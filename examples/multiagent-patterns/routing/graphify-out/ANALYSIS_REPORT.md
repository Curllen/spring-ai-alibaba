# Routing Examples - 完整知识图谱分析报告

---

## 📋 文档信息

| 属性 | 值 |
|------|-----|
| **项目名称** | Routing Examples |
| **分析日期** | 2026-05-29 |
| **分析路径** | /workspace/examples/multiagent-patterns/routing |
| **技术栈** | Java 17+, Spring Boot, Spring AI Alibaba, DashScope |
| **分析工具** | Graphify |
| **报告版本** | v1.0 |

---

## 一、项目概述

### 1.1 项目定位

本项目演示 Spring AI Alibaba 框架中的 **Routing 多 Agent 模式**——通过 LlmRoutingAgent 实现用户查询的自动分类和路由到对应专家 Agent（GitHub/Notion/Slack），支持 Simple（Classify→Parallel→Synthesize）和 Graph（StateGraph 子图节点）两种实现方式。

### 1.2 代码库规模

| 指标 | 数值 |
|------|------|
| **文件总数** | 23 |
| **代码量** | ~6,217 words |
| **图谱节点** | 191 |
| **图谱边** | 299 |
| **社区数量** | 19 |
| **提取置信度** | 95% EXTRACTED · 5% INFERRED |
| **Token 消耗** | 语义提取 Agent 调用 |

**按文件类型统计：**

| 文件类型 | 文件数 | 说明 |
|----------|--------|------|
| Java | 20 | 核心后端代码 |
| Markdown | 2 | simple/ 和 graph/ 子模块文档 |
| YAML | 1 | 应用配置 |

---

## 二、架构分析

### 2.1 两种 Routing 模式对比

```
┌──────────────────────────────────────────────────────────────────────┐
│                    LlmRoutingAgent（核心路由组件）                      │
├──────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  ┌─────────────────────────┐    ┌─────────────────────────────────┐  │
│  │  Simple Routing Pattern  │    │   Graph Routing Pattern          │  │
│  │  Classify → Parallel    │    │   START → preprocess → routing  │  │
│  │   → Synthesize           │    │     → postprocess → END         │  │
│  └───────────┬─────────────┘    └───────────────┬─────────────────┘  │
│              │                                   │                   │
│              ▼                                   ▼                   │
│  ┌───────────────────────┐    ┌───────────────────────────────────┐  │
│  │ RouterService 封装     │    │ StateGraph + PreprocessNode      │  │
│  │ RouterResult 聚合      │    │ + RoutingMergeNode + Postprocess │  │
│  └───────────────────────┘    └───────────────────────────────────┘  │
│                                                                      │
├──────────────────────────────────────────────────────────────────────┤
│              Specialist Agents: GitHub | Notion | Slack               │
│              Stub Tools (@Tool/@ToolParam annotations)                │
└──────────────────────────────────────────────────────────────────────┘
```

### 2.2 主要组件说明

#### Simple Routing Pattern（Community 0/5/1/9/7/12/15/16/17/18）
- **Community 5 - RoutingConfig**: 创建 githubAgent/notionAgent/slackAgent/routerAgent/routerService Bean。
- **Community 1 - RouterService**: 调用 LlmRoutingAgent，收集各 Agent 输出，LLM 合成最终答案返回 RouterResult。
- **Community 12/15/16 - Simple StubTools**: GitHub/Notion/Slack 的 @Tool 桩工具实现。
- **Community 17/18 - State Types**: Classification（source, query）和 AgentOutput（source, result）。

#### Graph Routing Pattern（Community 3/2/10/6/8/11/13/14）
- **Community 3 - RoutingGraphConfig**: 构建 StateGraph，将 LlmRoutingAgent 作为子图节点注册。
- **Community 2 - Graph Nodes**: PreprocessNode（查询验证/富化/元数据）和 PostprocessNode（格式化/元数据头）。
- **Community 10 - RoutingGraphService**: 封装 CompiledGraph 调用和结果处理。
- **Community 11/13/14 - Graph StubTools**: 共享的 GitHub/Notion/Slack 桩工具。

#### 共享基础设施
- **Community 0 - Routing Architecture**: 语义层核心概念（LlmRoutingAgent、两种模式、三个专家 Agent、并行执行、状态类型）。
- **Community 4 - Runners**: Simple 和 Graph 两个演示运行器。
- **Community 6/7 - AgentStaticLoaders**: Simple 和 Graph 各自的 Agent 自动发现加载器。

---

## 三、God Nodes（核心枢纽）

| 排名 | 节点 | 连接数 | 说明 |
|------|------|--------|------|
| 1 | **LlmRoutingAgent** | 平面节点（语义核心） | 核心路由组件，连接 Simple/Graph 两种模式和三个专家 Agent |
| 2 | **Tool** | 8+ | @Tool 注解，连接所有 StubTools 和 Agent |
| 3 | **StubTools (@Tool/@ToolParam)** | 6 | 工具桩基类，被 GitHub/Notion/Slack 三个 Agent 共享引用 |
| 4 | **RouterService** | 5+ | Simple 模式服务封装，聚合 RouterResult |
| 5 | **RoutingConfig** | 5+ | Simple 模式的 Bean 装配配置类 |
| 6 | **RoutingGraphConfig** | 5+ | Graph 模式的 StateGraph 配置类 |

---

## 四、关键连接与发现

### 4.1 核心发现

- **Simple/Graph 双模式共享 LlmRoutingAgent**：两种 Routing 模式使用同一个 LlmRoutingAgent 作为核心路由引擎，Simple 通过 RouterService 包装，Graph 通过 StateGraph.addNode 嵌入为子图节点。
- **RouterService ↔ RoutingMergeNode 语义相似**（0.8）：两者都是合成步骤，RouterService 在 Simple 模式中通过 LLM 合成输出，RoutingMergeNode 在 Graph 模式中通过 LLM 合成子 Agent 结果。
- **三专家 Agent 对称架构**：GitHubAgent/NotionAgent/SlackAgent 具有相同的结构（ReactAgent + StubTools），覆盖代码/文档/沟通三个知识域。
- **并行 Agent 执行**：框架的图结构并行条件边机制，使选中的专家 Agent 并发执行。
- **StubTools 的 Graph/Simple 重复**：两个子模块各自维护了一套 StubTools 副本（GitHub/Notion/Slack × 2），通过 @Tool 注解注入 Agent。

### 4.2 跨社区桥接节点

**LlmRoutingAgent** 连接 Community 0（语义核心）、Community 5（Simple Config）、Community 3（Graph Config）、Community 1（RouterService），是所有 Routing 功能的交汇点。

---

## 五、设计模式分析

| 模式名称(英文) | 模式名称(中文) | 涉及组件 | 置信度 |
|---------------|----------------|----------|--------|
| **Router Pattern** | **路由器模式** | LlmRoutingAgent, Specialist Agents | 1.0 |
| **Strategy Pattern** | **策略模式** | Simple Routing vs Graph Routing | 0.95 |
| **Pipeline Pattern** | **管线模式** | Preprocess→Routing→Postprocess | 1.0 |
| **Subgraph Pattern** | **子图模式** | LlmRoutingAgent as CompiledGraph in StateGraph | 1.0 |

---

## 六、社区分析

| 社区ID | 名称 | 内聚度 | 节点数 |
|--------|------|--------|--------|
| C18 | Classification: Source/Query Routing State | **0.50** | 1 |
| C17 | AgentOutput: Individual Agent Result State | **0.50** | 1 |
| C14 | Graph SlackStubTools | **0.44** | 5 |
| C13 | Graph NotionStubTools | **0.44** | 5 |
| C11 | Graph GitHubStubTools | **0.44** | 5 |
| C16 | Simple SlackStubTools | **0.44** | 5 |
| C15 | Simple NotionStubTools | **0.44** | 5 |
| C12 | Simple GitHubStubTools | **0.44** | 5 |
| C6 | Graph AgentStaticLoader | **0.43** | 8 |
| C7 | Simple AgentStaticLoader | **0.43** | 8 |
| C10 | RoutingGraphService: CompiledGraph Invocation | **0.41** | 5 |
| C5 | RoutingConfig: Simple Agent Beans | **0.33** | 9 |
| C3 | RoutingGraphConfig: StateGraph Assembly | **0.32** | 8 |
| C8 | RoutingGraphApplication | **0.27** | 5 |
| C9 | RoutingApplication | **0.27** | 5 |
| C4 | Routing Runners | **0.26** | 6 |
| C2 | Graph Nodes: Pre/Postprocess | **0.22** | 8 |
| C1 | RouterService: LlmRoutingAgent Invocation | **0.20** | 12 |
| C0 | Routing Architecture: Semantic Core | **0.11** | 21 |

---

## 七、知识缺口

**StubTools 重复**：Graph 和 Simple 各自维护一套 GitHub/Notion/Slack StubTools（C11-C16），生产环境建议提取为共享模块避免代码重复。

---

## 八、关键问题与建议

| 优先级 | 建议 | 理由 |
|--------|------|------|
| 🟡 中 | StubTools 提取为共享模块 | 当前 Graph/Simple 各自复制了相同的 StubTools 代码 |
| 🟡 中 | 考虑路由失败降级策略 | 当 LLM 分类不确定时，兜底路由和错误处理机制需明确 |
| 🟢 低 | Graph 模式增加可观测性 | PreprocessNode 已有 traceId 支持，可扩展到子 Agent 执行追踪 |

---

## 九、推荐深度探索问题

1. **Simple vs Graph Routing 的选择条件**：何时用 Simple 模式（RouterService 封装），何时用 Graph 模式（StateGraph 子图）？各自的性能和扩展性差异如何？
2. **LlmRoutingAgent 的分类精度**：当查询跨域（同时涉及 GitHub 和 Notion）时，LLM 分类器能否正确识别多目标路由？
3. **Parallel Agent 的超时和错误处理**：三个专家 Agent 并行执行时，某个超时或失败如何处理？是否有部分成功的策略？
4. **RoutingMergeNode 的合成质量**：LLM 合成多 Agent 输出时，如何确保不丢失关键信息或引入幻觉？
5. **AgentStaticLoader 的注册顺序**：Graph 和 Simple 的 AgentStaticLoader 是否会冲突？Studio 如何区分两个模块的 Agent？

---

## 十、输出文件清单

| 文件 | 大小 | 用途 |
|------|------|------|
| `graph.html` | 172 KB | 交互式知识图谱可视化 |
| `graph.json` | 158 KB | 原始图谱数据 |
| `GRAPH_REPORT.md` | 8 KB | 审计报告 |
| `ANALYSIS_REPORT.md` | (本文件) | 标准化分析报告 |

---

## 📁 文件引用

- [graph.html](graphify-out/graph.html) - 交互式图谱
- [graph.json](graphify-out/graph.json) - 图谱数据
- [GRAPH_REPORT.md](graphify-out/GRAPH_REPORT.md) - 原始报告

---

*Generated by Graphify - Knowledge Graph Analysis Tool*
*报告生成模式: AST 结构提取 + Agent 语义分析*
