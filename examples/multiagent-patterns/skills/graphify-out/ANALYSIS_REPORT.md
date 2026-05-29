# Skills (Progressive Disclosure) Example - 完整知识图谱分析报告

---

## 📋 文档信息

| 属性 | 值 |
|------|-----|
| **项目名称** | Skills (Progressive Disclosure) Example |
| **分析日期** | 2026-05-29 |
| **分析路径** | /workspace/examples/multiagent-patterns/skills |
| **技术栈** | Java 17+, Spring Boot, Spring AI Alibaba, DashScope |
| **分析工具** | Graphify |
| **报告版本** | v1.0 |

---

## 一、项目概述

### 1.1 项目定位

本项目演示 Spring AI Alibaba 框架中的 **Skills (Progressive Disclosure) 模式**——通过 ClasspathSkillRegistry + SkillsAgentHook + ReactAgent 构建一个 SQL 助手，Agent 在系统提示中仅看到技能描述摘要，按需通过 `read_skill` 工具加载完整的 SKILL.md 内容（表结构、业务逻辑、示例查询）。

### 1.2 代码库规模

| 指标 | 数值 |
|------|------|
| **文件总数** | 8 |
| **代码量** | ~1,911 words |
| **图谱节点** | 67 |
| **图谱边** | 106 |
| **社区数量** | 7 |
| **提取置信度** | 95% EXTRACTED · 5% INFERRED |
| **Token 消耗** | 语义提取 Agent 调用 |

**按文件类型统计：**

| 文件类型 | 文件数 | 说明 |
|----------|--------|------|
| Java | 4 | 核心后端代码（Config/Application/Runner/AgentStaticLoader） |
| Markdown | 3 | README.md + 2 个 SKILL.md 技能文档 |
| YAML | 1 | 应用配置文件 |

---

## 二、架构分析

### 2.1 核心架构层次

```
┌────────────────────────────────────────────────────────────────┐
│                      应用入口层                                 │
│   SkillsApplication  │  SkillsRunner (Demo)                    │
│   AgentStaticLoader (Studio Discovery)                        │
├────────────────────────────────────────────────────────────────┤
│                    配置装配层                                   │
│   SkillsConfig: SkillRegistry Bean + SkillsAgentHook          │
│        + sqlAssistantAgent (ReactAgent)                       │
├────────────────────────────────────────────────────────────────┤
│                 框架技能基础设施层                               │
│   ClasspathSkillRegistry (loads skills/ directory)            │
│   SkillsAgentHook (provides read_skill + SkillsInterceptor)   │
│   SkillsInterceptor (injects Available Skills into prompt)    │
├────────────────────────────────────────────────────────────────┤
│                    技能内容层（SKILL.md）                        │
│   sales_analytics/SKILL.md    │   inventory_management/SKILL.md │
│   YAML frontmatter + schema   │   YAML frontmatter + schema    │
│   + business rules + SQL      │   + business rules + SQL       │
└────────────────────────────────────────────────────────────────┘
```

### 2.2 Progressive Disclosure 运行时流程

```
START
  │
  ▼
┌──────────────────────────────────────┐
│ SkillsInterceptor 注入系统提示          │
│ "Available Skills:" 段落               │
│ (仅含 name + description 摘要)         │
└──────────────┬───────────────────────┘
               │
               ▼
┌──────────────────────────────────────┐
│ ReactAgent (sqlAssistantAgent)        │
│ 接收用户查询, 判断是否需要 Skill 详情     │
│ 如需: 调用 read_skill("sales_analytics")│
│ 或 read_skill("inventory_management")  │
└──────────────┬───────────────────────┘
               │
               ▼
┌──────────────────────────────────────┐
│ read_skill 返回完整 SKILL.md 内容       │
│ (schema + business rules + SQL examples│
└──────────────┬───────────────────────┘
               │
               ▼
┌──────────────────────────────────────┐
│ Agent 基于 Skill 指导执行 SQL 查询       │
│ (ToolContext + DataSource)            │
└──────────────────────────────────────┘
```

### 2.3 两个 Skill 对比

| 特性 | sales_analytics | inventory_management |
|------|----------------|---------------------|
| 表数量 | 3 (customers, orders, order_items) | 4 (products, warehouses, inventory, stock_movements) |
| 业务规则 | 活跃客户、收入计算、高价值订单 | 可用库存、补货判定、活跃产品过滤 |
| 关键 ER | customers → orders → order_items | products ← inventory → warehouses, products ← stock_movements → warehouses |
| 示例查询 | Top-10 客户季度收入 | 低于补货点产品列表 |

---

## 三、God Nodes（核心枢纽）

| 排名 | 节点 | 连接数 | 说明 |
|------|------|--------|------|
| 1 | **sales_analytics Skill** | 7 | 含 3 张表 + 3 条规则 + 示例查询 |
| 2 | **inventory_management Skill** | 7 | 含 4 张表 + 3 条规则 + 示例查询 |
| 3 | **SkillsConfig** | 5 | 装配 SkillRegistry + SkillsAgentHook + sqlAssistantAgent |
| 4 | **SkillsAgentHook** | 4 | 提供 read_skill + 注册 SkillsInterceptor |
| 5 | **ClasspathSkillRegistry** | 4 | 从 classpath 加载 skills/ 目录 |
| 6 | **ReactAgent (sqlAssistantAgent)** | 3 | 核心 SQL 助手，使用 .hooks() 集成技能 |
| 7 | **products Table** | 3 | 连接 inventory 和 stock_movements 两个子表 |

---

## 四、关键连接与发现

### 4.1 核心发现

- **Progressive Disclosure 三组件链**：ClasspathSkillRegistry（加载）→ SkillsAgentHook（提供工具 + 拦截）→ ReactAgent（使用 .hooks() 集成）构成完整的 Framework Skill Loading Chain（Hyperedge）。

- **两个 Skill 的语义对称性**（0.85）：sales_analytics 和 inventory_management 结构相同（YAML frontmatter + schema + rules + SQL），构成对称的业务域补充。

- **SKILL.md 标准化格式**：每个技能目录下放置 SKILL.md 文件，YAML frontmatter 定义 name/description（用于系统提示摘要），Markdown body 包含完整 schema/rules/SQL（用于 read_skill 加载）。

- **SkillsInterceptor 的 Prompt 增强**：在模型系统消息中动态注入 "Available Skills" 段落，仅含每个 Skill 的 name + description 摘要，保持初始上下文精简。

- **跨域业务规则相似性**：Revenue Calculation Rule 与 Available Stock Rule 语义相似（0.60）；High-Value Order Rule 与 Reorder Rule 语义相似（0.65）——两个 Skill 共享分类过滤模式。

### 4.2 跨社区桥接节点

**SKILL.md Format** 连接 Community 1（框架基础设施）和 Community 3/5（两个具体 Skill），是标准化文件协议的定义点。

---

## 五、设计模式分析

| 模式名称(英文) | 模式名称(中文) | 涉及组件 | 置信度 |
|---------------|----------------|----------|--------|
| **Progressive Disclosure** | **渐进式披露** | SkillsInterceptor + read_skill + SKILL.md | 1.0 |
| **Skill Registry Pattern** | **技能注册模式** | ClasspathSkillRegistry + skills/ directory | 1.0 |
| **Hook Pattern** | **Hook 模式** | SkillsAgentHook (provides tools + interceptors) | 1.0 |
| **Interceptor Pattern** | **拦截器模式** | SkillsInterceptor (system prompt injection) | 1.0 |

---

## 六、社区分析

| 社区ID | 名称 | 内聚度 | 节点数 |
|--------|------|--------|--------|
| C0 | AgentStaticLoader: Agent Discovery & Loading | **0.44** | 12 |
| C6 | SkillsRunner: Demo Execution & RunnableConfig | **0.28** | 8 |
| C4 | SkillsApplication: Spring Boot Entry & Lifecycle | **0.24** | 9 |
| C3 | Inventory Management Skill: Tables & Rules | **0.17** | 9 |
| C5 | Sales Analytics Skill: Tables & Rules | **0.17** | 8 |
| C2 | SkillsConfig: Skill Registry & Hook Assembly | **0.12** | 10 |
| C1 | Progressive Disclosure Framework: Semantic Core | **0.10** | 11 |

---

## 七、知识缺口

无显著知识缺口。8 文件 67 节点的小型模块架构清晰，Progressive Disclosure 的三层抽象（Registry → Hook → Agent）完整可追溯。

---

## 八、关键问题与建议

| 优先级 | 建议 | 理由 |
|--------|------|------|
| 🟡 中 | 添加 Dynamic Skill 加载机制 | 当前仅支持 classpath 静态加载，建议支持远程/数据库 Skill 源 |
| 🟢 低 | SKILL.md 补充版本管理字段 | YAML frontmatter 可添加 version/author 元数据 |
| 🟢 低 | 增加 Skill 冲突检测 | 当多个 Skill 的 name 冲突时需有检测和报错机制 |

---

## 九、推荐深度探索问题

1. **Progressive Disclosure vs Traditional System Prompt**：与直接将所有 Schema 写入系统提示相比，渐进式披露在 Token 消耗和响应质量上的量化差异如何？
2. **read_skill 的缓存策略**：同一会话中多次调用 read_skill 是否会重复加载？框架是否支持 Skill 内容缓存？
3. **多 Skill 的交叉查询**：当用户查询同时涉及 sales_analytics 和 inventory_management（如"哪些畅销产品需要补货"），Agent 如何处理跨 Skill 的 SQL 组合？
4. **SKILL.md 的热重载**：如果运行时修改了 SKILL.md 文件，是否需要重启 Agent？是否支持动态重新加载？
5. **Skill 的权限控制**：多租户场景下，不同 Agent 是否应该看到不同的 Skill 列表？框架是否支持 Skill 级别的访问控制？

---

## 十、输出文件清单

| 文件 | 大小 | 用途 |
|------|------|------|
| `graph.html` | 65 KB | 交互式知识图谱可视化 |
| `graph.json` | 53 KB | 原始图谱数据 |
| `GRAPH_REPORT.md` | 7 KB | 审计报告 |
| `ANALYSIS_REPORT.md` | (本文件) | 标准化分析报告 |

---

## 📁 文件引用

- [graph.html](graphify-out/graph.html) - 交互式图谱
- [graph.json](graphify-out/graph.json) - 图谱数据
- [GRAPH_REPORT.md](graphify-out/GRAPH_REPORT.md) - 原始报告

---

*Generated by Graphify - Knowledge Graph Analysis Tool*
*报告生成模式: AST 结构提取 + Agent 语义分析*
