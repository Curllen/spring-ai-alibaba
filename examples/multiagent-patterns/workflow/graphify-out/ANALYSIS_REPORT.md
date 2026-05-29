# Multi-Agent Workflow (RAG + SQL Agents) - 完整知识图谱分析报告

---

## 📋 文档信息

| 属性 | 值 |
|------|-----|
| **项目名称** | Spring AI Alibaba Workflow Pattern - Multi-Agent RAG & SQL Agents |
| **分析日期** | 2026-05-29 |
| **分析路径** | /workspace/examples/multiagent-patterns/workflow |
| **技术栈** | Java 17+, Spring Boot, Spring AI Alibaba, DashScope, H2, StateGraph |
| **分析工具** | Graphify |
| **报告版本** | v1.0 |

---

## 一、项目概述

### 1.1 项目定位

Workflow 模式样本项目，实现两种 **StateGraph 工作流**：
- **RAG Agent**: Query → Rewrite → Retrieve → Prepare → Agent → Response 管道式工作流
- **SQL Agent**: Question → Agent (list_tables → get_schema → run_query) → Answer 状态机工作流

两种工作流基于 Spring AI Alibaba StateGraph API 构建，通过 feature flag 独立运行。RAG 工作流使用 DashScope EmbeddingModel 进行向量检索，SQL 工作流使用 H2 内存数据库的 Chinook 模式。

### 1.2 代码库规模

| 指标 | 数值 |
|------|------|
| **文件总数** | 20 |
| **代码量** | ~4,791 words |
| **图谱节点** | 166 |
| **图谱边** | 266 (去重) / 559 (原始提取) |
| **社区数量** | 13 |
| **提取置信度** | 93.4% EXTRACTED · 6.6% INFERRED |
| **Token 消耗** | 0 input / 0 output |

**按文件类型统计：**

| 文件类型 | 文件数 | 说明 |
|----------|--------|------|
| Java | 15 | 后端核心代码（Config×3、Runner×2、Service×2、Node×5、Tools×2、App） |
| Markdown | 3 | README + 2 个子模块文档 |
| YAML | 1 | Spring Boot 应用配置 |
| SQL | 1 | Chinook 数据库初始化脚本 |

---

## 二、架构分析

### 2.1 核心架构层次

```
┌──────────────────────────────────────────────────────────────────┐
│               Documentation Layer（文档层）                        │
│   README.md  │  ragagent/README.md  │  sqlagent/README.md        │
├──────────────────────────────────────────────────────────────────┤
│               Configuration Layer（配置层）                        │
│   RagAgentConfig  │  SqlAgentConfig  │  WorkflowAgentLoaderConfig│
├──────────────────────────────────────────────────────────────────┤
│               Service Layer（服务层）                              │
│   RagAgentService  │  SqlAgentService                            │
├──────────────────────────────────────────────────────────────────┤
│               Node Layer（工作流节点层）                            │
│   RAG: RewriteNode → RetrieveNode → PrepareAgentNode             │
│   SQL: ListTablesNode → CallGetSchemaNode → getSchemaNode        │
├──────────────────────────────────────────────────────────────────┤
│               Tool Layer（工具层）                                 │
│   SqlTools (list_tables, get_schema, run_query)                  │
│   RagAgentTools (get_latest_news)                                 │
├──────────────────────────────────────────────────────────────────┤
│               Runtime Layer（运行时层）                            │
│   WorkflowApplication  │  RagAgentRunner  │  SqlAgentRunner       │
└──────────────────────────────────────────────────────────────────┘
```

### 2.2 双工作流架构图

```
                  ┌─────────────────────────────────────┐
                  │      WorkflowApplication            │
                  │  @SpringBootApplication             │
                  └──────────┬──────────────────────────┘
                             │ conditionally starts
            ┌────────────────┼────────────────┐
            ▼                                 ▼
   ┌─────────────────────┐        ┌─────────────────────┐
   │    RagAgentRunner    │        │   SqlAgentRunner    │
   │ (workflow.rag=true)  │        │ (workflow.sql=true) │
   └──────────┬──────────┘        └──────────┬──────────┘
              │                               │
   ┌──────────▼──────────┐        ┌──────────▼──────────┐
   │   RagAgentService   │        │   SqlAgentService   │
   │     .run(query)     │        │     .run(question)  │
   └──────────┬──────────┘        └──────────┬──────────┘
              │                               │
   RAG StateGraph:                  SQL StateGraph:
   ┌──────────┐                    ┌──────────────────┐
   │ Rewrite  │                    │  ListTablesNode  │  ← deterministic
   └────┬─────┘                    └────────┬─────────┘
        ▼                                    ▼
   ┌──────────┐                    ┌──────────────────┐
   │ Retrieve │                    │ CallGetSchemaNode│  ← forces sql_db_schema
   └────┬─────┘                    └────────┬─────────┘
        ▼                                    ▼
   ┌──────────┐                    ┌──────────────────┐
   │ Prepare  │                    │ getSchemaNode    │
   └────┬─────┘                    └────────┬─────────┘
        ▼                                    ▼
   ┌──────────────────┐            ┌──────────────────────┐
   │ ReactAgent       │            │ generateQueryAgent   │
   │ + get_latest_news│            │ (ReactAgent + SqlTools)│
   └──────────────────┘            │ SELECT only!          │
                                   └──────────────────────┘
```

### 2.3 主要组件说明

#### 文档与模式定义层
- **Community 0 - Workflow Patterns: RAG & SQL Agent Concepts** (内聚度 **0.134** ⚠️)
  - 24 个语义文档节点，涵盖 RAG/SQL 两种工作流的概念定义
  - 包含 StateGraph、ReactAgent、DashScope API、EmbeddingModel 等核心概念
  - 3 个引用文档连接（multiagents/custom.md, rag-agent-workflow.md, sql-agent-workflow.md）

#### RAG 工作流组件
- **Community 1 - RAG Pipeline Nodes: Prepare, Retrieve & VectorStore** (内聚度 0.129)
  - PrepareAgentNode: 将检索上下文和问题格式化为提示词
  - RetrieveNode: 向量相似度搜索（确定性节点，不调用 LLM）
  - NodeAction: 工作流节点接口实现
- **Community 4 - RagAgentConfig: RAG Graph & Bean Wiring** (内聚度 0.321)
  - RagAgentConfig: 构建 RAG StateGraph (ragGraph)，装配 ragAgent、ragAgentService、ragVectorStore
- **Community 8 - RewriteNode: LLM Query Rewriting** (内聚度 0.289)
  - RewriteNode: 使用 ChatModel 重写用户查询以提高检索精度
- **Community 9 - RagAgentService: RAG Graph Execution** (内聚度 0.333)
  - RagAgentService: 封装 CompiledGraph 调用，提供 run() 方法
- **Community 12 - RagAgentTools: News Retrieval Tool** (内聚度 0.500)
  - RagAgentTools: get_latest_news @Tool 方法，RAG Agent 的外部数据源

#### SQL 工作流组件
- **Community 3 - SqlTools: SQL Database Tool Methods** (内聚度 0.235)
  - SqlTools: 3 个 @Tool 方法——list_tables、get_schema、run_query
  - 通过 JdbcTemplate 操作 H2 内存数据库
  - 仅允许 SELECT 查询，禁止 DML 操作
- **Community 5 - SqlAgentConfig: SQL Graph & Bean Wiring** (内聚度 0.333)
  - SqlAgentConfig: 构建 SQL StateGraph (sqlGraph)，装配 generateQueryAgent、sqlAgentService、sqlTools
- **Community 6 - CallGetSchemaNode: Forced Schema Tool Invocation** (内聚度 0.255)
  - CallGetSchemaNode: 强制 LLM 调用 sql_db_schema 工具的中间节点（非 ReactAgent 自由选择）
- **Community 7 - ListTablesNode: Deterministic Table Discovery** (内聚度 0.267)
  - ListTablesNode: 确定性节点，直接调用 list_tables 获取数据库表名，不调用 LLM
- **Community 10 - SqlAgentService: SQL Graph Execution** (内聚度 0.333)
  - SqlAgentService: 封装 CompiledGraph 调用，提供 run() 方法

#### 基础设施层
- **Community 2 - Application Entry & Agent Runners** (内聚度 0.124)
  - WorkflowApplication: Spring Boot 入口，ApplicationReadyEvent 监听器
  - RagAgentRunner / SqlAgentRunner: ApplicationListener + ApplicationRunner 实现
- **Community 11 - WorkflowAgentLoaderConfig: Studio Agent Registry** (内聚度 0.533)
  - WorkflowAgentLoaderConfig: AgentStaticLoader 工厂，暴露给 Spring AI Studio

---

## 三、God Nodes（核心枢纽）

### 3.1 最重要的节点

| 排名 | 节点 | 连接数 | 说明 |
|------|------|--------|------|
| 1 | **SqlTools** | 11 | SQL 工具类，3 个 @Tool 方法，连接所有 SQL 节点 |
| 2 | **RAG Agent Workflow** | 10 | RAG 工作流概念节点，连接所有 RAG 组件 |
| 3 | **SQL Agent Workflow** | 10 | SQL 工作流概念节点，连接所有 SQL 组件 |
| 4 | **ToolCallback** | 7 | Spring AI 工具回调接口，连接多个代理配置 |
| 5 | **RagAgentConfig** | 6 | RAG 图配置与 Bean 装配 |
| 6 | **SqlAgentConfig** | 5 | SQL 图配置与 Bean 装配 |
| 7 | **Multi-Agent Workflow Pattern** | 5 | 顶层模式概念节点 |

### 3.2 核心抽象分析

**SqlTools**：连接数 11 的顶级 God Node，是整个 SQL 工作流的工具枢纽。3 个 @Tool 方法（list_tables、get_schema、run_query）被 4 个工作流节点和 1 个 ReactAgent 调用。通过 JdbcTemplate 操作 H2 内存数据库，实现了数据库操作的完整封装。

**RAG Agent Workflow**：连接数 10 的概念枢纽节点，定义了 Query → Rewrite → Retrieve → Prepare → Agent 的管道式工作流。每个步骤对应一个 StateGraph Node，节点间通过 OverallState 传递数据。

**SQL Agent Workflow**：与 RAG Workflow 对称的概念节点（同为 deg=10），定义了 list_tables → get_schema → run_query 的工具链式工作流。两个概念通过 semantically_similar_to 边连接（INFERRED, 0.80），表明二者共享基于 ReactAgent 的核心模式。

---

## 四、关键连接与发现

### 4.1 核心发现

- **双 StateGraph 架构**：RAG 和 SQL 工作流各自维护独立的 StateGraph (ragGraph / sqlGraph)，共享 WorkflowApplication 入口但通过 feature flag 独立运行。这种设计使两种工作流可以独立开发、测试和部署。

- **确定性 vs LLM 节点策略**：ListTablesNode 和 RetrieveNode 被设计为确定性节点（不调用 LLM），而 RewriteNode 和 CallGetSchemaNode 调用 ChatModel。展示了在 StateGraph 中混合确定性和 LLM 驱动节点的最佳实践。

- **强制工具选择**：CallGetSchemaNode 不依赖 ReactAgent 的工具选择，而是直接调用 sql_db_schema。这种做法避免了 LLM 在复杂 SQL 场景下的工具选择错误，提供了更强的控制力。

- **SELECT-only 安全约束**：SqlTools.run_query 仅允许 SELECT 语句，通过正则匹配禁止 INSERT/UPDATE/DELETE/DROP 等 DML 操作。这种白名单安全策略值得在类似场景中推广。

### 4.2 意外连接（Surprising Connections）

| 源节点 | 关系 | 目标节点 | 置信度 | 说明 |
|--------|------|----------|--------|------|
| `RAG Agent Workflow` | semantically_similar_to | `SQL Agent Workflow` | INFERRED (0.80) | 两种工作流共享 ReactAgent + StateGraph 模式，但文件中无显式引用 |
| `SQL Agent Workflow` | conceptually_related_to | `DashScope API` | INFERRED | SQL 工作流文档未提及依赖 DashScope，但实际通过 ChatModel 配置依赖 |
| `EmbeddingModel` | conceptually_related_to | `Vector Search` | INFERRED | EmbeddingModel 来自 DashScope starter，Vector Search 是 RAG 节点 |

### 4.3 跨社区桥接节点

**SqlTools**（介数中心性 0.311）连接了 **Community 3-7-10** 三个 SQL 社区，是整个 SQL 工作流的核心桥接。ListTablesNode、CallGetSchemaNode 和 generateQueryAgent 都通过 SqlTools 访问数据库，形成星型依赖结构。

**RewriteNode**（介数中心性 0.040）连接了 **Community 8 和 Community 1**，是 RAG 工作流中输入处理与检索准备之间的桥梁。

---

## 五、设计模式分析

### 5.1 已识别的设计模式

| 模式名称(英文) | 模式名称(中文) | 涉及组件 | 置信度 |
|-------------|----------|----------|--------|
| **StateGraph Pattern** | **状态图模式** | RagAgentConfig.ragGraph(), SqlAgentConfig.sqlGraph() | 1.0 |
| **Pipeline Pattern** | **管道模式** | RAG: Rewrite → Retrieve → Prepare → Agent | 1.0 |
| **Tool-Chain Pattern** | **工具链模式** | SQL: list_tables → get_schema → run_query | 1.0 |
| **Builder Pattern** | **建造者模式** | StateGraph.builder(), ReactAgent.builder() | 1.0 |
| **Strategy Pattern** | **策略模式** | AgentLoader 接口 → AgentStaticLoader 实现 | 0.9 |
| **Template Method Pattern** | **模板方法模式** | NodeAction.apply() 统一接口 | 0.9 |
| **Security-By-Design** | **安全设计** | run_query SELECT-only 白名单 | 1.0 |
| **Feature Flag Pattern** | **特性开关模式** | workflow.rag.enabled / workflow.sql.enabled | 1.0 |

### 5.2 关键类层次结构

```
NodeAction (接口)
    ├── RewriteNode.apply()         ← LLM 查询重写
    ├── RetrieveNode.apply()        ← 向量检索（确定性）
    ├── PrepareAgentNode.apply()    ← 上下文格式化
    ├── ListTablesNode.apply()      ← 表名查询（确定性）
    └── CallGetSchemaNode.apply()   ← 强制 Schema 工具调用

ApplicationListener<ApplicationReadyEvent> (接口)
    ├── RagAgentRunner.onReady()    ← 条件启动 RAG 工作流
    └── SqlAgentRunner.onReady()    ← 条件启动 SQL 工作流

AgentLoader (接口)
    └── WorkflowAgentLoaderConfig   ← Studio 代理注册
```

---

## 六、社区分析

### 6.1 主要社区分布

| 社区ID | 名称 | 内聚度 | 节点数 | 说明 |
|--------|------|--------|--------|------|
| 0 | Workflow Patterns: RAG & SQL Agent Concepts | **0.134** ⚠️ | 24 | 文档概念层，RAG/SQL 模式定义 |
| 1 | RAG Pipeline Nodes: Prepare, Retrieve & VectorStore | **0.129** ⚠️ | 20 | PrepareAgentNode + RetrieveNode |
| 2 | Application Entry & Agent Runners | **0.124** ⚠️ | 21 | Application + Runners + Listeners |
| 3 | SqlTools: SQL Database Tool Methods | 0.235 | 18 | 3 个 @Tool SQL 方法 |
| 4 | RagAgentConfig: RAG Graph & Bean Wiring | 0.321 | 13 | RAG StateGraph 构建 |
| 5 | SqlAgentConfig: SQL Graph & Bean Wiring | 0.333 | 13 | SQL StateGraph 构建 |
| 6 | CallGetSchemaNode: Forced Schema Tool Invocation | 0.255 | 11 | 强制 schema 工具调用节点 |
| 7 | ListTablesNode: Deterministic Table Discovery | 0.267 | 10 | 确定性表发现节点 |
| 8 | RewriteNode: LLM Query Rewriting | 0.289 | 10 | LLM 查询重写节点 |
| 9 | RagAgentService: RAG Graph Execution | 0.333 | 7 | RAG CompiledGraph 封装 |
| 10 | SqlAgentService: SQL Graph Execution | 0.333 | 7 | SQL CompiledGraph 封装 |
| 11 | WorkflowAgentLoaderConfig: Studio Agent Registry | **0.533** | 6 | Studio 代理注册 |
| 12 | RagAgentTools: News Retrieval Tool | 0.500 | 5 | get_latest_news @Tool |

### 6.2 低内聚度社区（需关注）

| 社区ID | 内聚度 | 问题描述 |
|--------|--------|----------|
| 2 | 0.124 | Application Entry & Agent Runners 包含 21 个节点，混合了 WorkflowApplication、两个 Runner 和基础设施节点。高 AST 节点密度导致内聚度极低 |
| 1 | 0.129 | RAG Pipeline Nodes 混合了 PrepareAgentNode 和 RetrieveNode 的 AST 节点，包含大量 Map/String/Object 等 Java 类型引用 |
| 0 | 0.134 | Workflow Patterns 概念社区涵盖 24 个文档节点，RAG 和 SQL 概念未分离，可拆分为两个子社区 |

---

## 七、知识缺口（Knowledge Gaps）

### 7.1 薄弱社区

Community 12 (5 节点, 内聚度 0.500) 和 Community 11 (6 节点, 内聚度 0.533) 节点数较少但内聚度高，属于功能明确的小型社区，不需要合并。

### 7.2 潜在设计债务

1. **RAG 工作流硬编码 RAG 提示词**：RagAgentConfig.buildAgentPrompt() 中的 prompt 模板尚未实现（TODO 占位符），完成后可能增加节点数和社区复杂度。
2. **向量存储依赖未明确**：RetrieveNode 依赖 VectorStore，但 VectorStore 的初始化逻辑在 RagAgentConfig.ragVectorStore() 中，与 RAG 工作流的其他节点不在同一社区。

---

## 八、关键问题与建议

### 8.1 架构优化建议

| 优先级 | 建议 | 理由 |
|--------|------|------|
| 🟡 中 | 将 RAG 和 SQL 的文档概念拆分到独立社区 | Community 0 内聚度 0.134，两种工作流概念混杂 |
| 🟡 中 | 从 Application & Runners 社区中分离基础设施节点 | Community 2 内聚度 0.124，21 个节点中混合了应用层和运行时层 |
| 🟢 低 | 考虑将 RagAgentConfig 和 SqlAgentConfig 中的 VectorStore/JdbcTemplate 初始化抽取 | 两个配置类各自管理外部依赖的初始化，可抽取为共享 DataSourceConfig |
| 🟢 低 | 为 SqlTools.run_query 的 SELECT 白名单增加单元测试 | 安全白名单策略目前只有代码级约束，需要测试覆盖 |

### 8.2 具体改进方案

针对内聚度问题：
1. 将 Community 0 拆分为 "RAG Workflow Concepts" 和 "SQL Workflow Concepts" 两个子主题
2. 将 Community 2 中的 RagAgentRunner 和 SqlAgentRunner 独立为各自的子社区
3. 补充 RAG 工作流节点的 prompt 模板实现（目前为 TODO），完成后重新评估社区划分

---

## 九、推荐深度探索问题

1. **StateGraph 与 AgentTool/TaskTool 的关系？**：Workflow 模式使用 StateGraph 定义工作流，Supervisor 模式使用 AgentTool，Routing 模式也使用 StateGraph。这三种模式在 StateGraph 的使用方式上有何异同？
2. **CallGetSchemaNode 的强制工具调用是否可泛化为可复用模式？**：不依赖 ReactAgent 的工具选择，直接强制调用特定工具的做法，是否可以抽取为通用的 ForcedToolInvocationNode？
3. **确定性节点与 LLM 节点的混合策略**：ListTablesNode 和 RetrieveNode 是确定性的，而 RewriteNode 和 CallGetSchemaNode 调用 LLM。判断一个节点应使用哪种策略的标准是什么？
4. **向量存储的初始化和生命周期**：RagAgentConfig 中的 VectorStore 在当前实现中为空（TODO），未来使用什么向量存储（Chroma/Milvus/PGVector）会影响哪些节点？
5. **跨模式模块复用**：Workflow 模式的 NodeAction 接口、OverallState 状态对象和 StateGraph 构建模式是否可以提取为可复用的框架层？

---

## 十、输出文件清单

| 文件 | 大小 | 用途 |
|------|------|------|
| `graph.html` | ~140 KB | 交互式知识图谱可视化（浏览器打开） |
| `graph.json` | ~130 KB | 原始图谱数据（JSON 格式） |
| `GRAPH_REPORT.md` | ~8 KB | 自动生成的审计报告 |
| `ANALYSIS_REPORT.md` | ~10 KB | 标准化分析报告（本文件） |
| `manifest.json` | - | 分析文件清单 |
| `cost.json` | - | Token 消耗记录 |

---

## 📁 文件引用

- [graph.html](graphify-out/graph.html) - 交互式图谱
- [graph.json](graphify-out/graph.json) - 图谱数据
- [GRAPH_REPORT.md](graphify-out/GRAPH_REPORT.md) - 原始报告
- [manifest.json](graphify-out/manifest.json) - 文件清单

---

*Generated by Graphify - Knowledge Graph Analysis Tool*
*报告生成模式: AST 结构提取 + Agent 语义分析*