# Graph Report - /workspace/examples/documentation  (2026-05-28)

## Corpus Check
- Corpus is ~41,635 words - fits in a single context window. You may not need a graph.

## Summary
- 993 nodes · 1933 edges · 45 communities (37 shown, 8 thin omitted)
- Extraction: 96% EXTRACTED · 4% INFERRED · 0% AMBIGUOUS · INFERRED: 86 edges (avg confidence: 0.72)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Tutorial Agents ReAct Hooks & Agent Commands|Tutorial Agents: ReAct Hooks & Agent Commands]]
- [[_COMMUNITY_Tutorial MCP & Tools ToolCallback & Remote Services|Tutorial MCP & Tools: ToolCallback & Remote Services]]
- [[_COMMUNITY_Tutorial Structured Output Entities & Type Mappings|Tutorial Structured Output: Entities & Type Mappings]]
- [[_COMMUNITY_Tutorial Hooks & Interceptors Agent Lifecycle Management|Tutorial Hooks & Interceptors: Agent Lifecycle Management]]
- [[_COMMUNITY_Graph Checkpoint Redis Saver & State Persistence|Graph Checkpoint: Redis Saver & State Persistence]]
- [[_COMMUNITY_Graph Quickstart BugTracking & Intent Classification Nodes|Graph Quickstart: BugTracking & Intent Classification Nodes]]
- [[_COMMUNITY_Tutorial Memory ChatModel & Agent Message History|Tutorial Memory: ChatModel & Agent Message History]]
- [[_COMMUNITY_Multi-Agent Supervisor CodeRequest & CoderReviewer Nodes|Multi-Agent Supervisor: CodeRequest & Coder/Reviewer Nodes]]
- [[_COMMUNITY_A2A Config AgentLoader & Data Analysis Agent Beans|A2A Config: AgentLoader & Data Analysis Agent Beans]]
- [[_COMMUNITY_Core Streaming ProcessStreamingNode & State Graph|Core Streaming: ProcessStreamingNode & State Graph]]
- [[_COMMUNITY_README Documentation Module Overview & Feature Index|README Documentation: Module Overview & Feature Index]]
- [[_COMMUNITY_Human-in-the-Loop ContinueExecution & Interrupt Patterns|Human-in-the-Loop: ContinueExecution & Interrupt Patterns]]
- [[_COMMUNITY_Advanced RAG KnowledgeBase, TwoStep & Agentic RAG|Advanced RAG: KnowledgeBase, TwoStep & Agentic RAG]]
- [[_COMMUNITY_Advanced Workflow Parallel Aggregator & Routing Agent|Advanced Workflow: Parallel Aggregator & Routing Agent]]
- [[_COMMUNITY_Advanced Memory Tool ReadWrite & Model Hook Memory|Advanced Memory: Tool Read/Write & Model Hook Memory]]
- [[_COMMUNITY_Tutorial Messages AudioInput & Assistant Messages|Tutorial Messages: AudioInput & Assistant Messages]]
- [[_COMMUNITY_Advanced HumanInTheLoop ApproveEditTool Decisions|Advanced HumanInTheLoop: Approve/Edit/Tool Decisions]]
- [[_COMMUNITY_Advanced Tool Selection Optional Tools & OverallState|Advanced Tool Selection: Optional Tools & OverallState]]
- [[_COMMUNITY_Agent as Tool AgentToolExample with Input Schema|Agent as Tool: AgentToolExample with Input Schema]]
- [[_COMMUNITY_Advanced Multi-Agent SequentialParallel & Custom Merge|Advanced Multi-Agent: Sequential/Parallel & Custom Merge]]
- [[_COMMUNITY_Subgraph as NodeAction Subgraph Compilation & Execution|Subgraph as NodeAction: Subgraph Compilation & Execution]]
- [[_COMMUNITY_Tutorial Agents BasicAdvanced Model Config & Streaming|Tutorial Agents: Basic/Advanced Model Config & Streaming]]
- [[_COMMUNITY_Tutorial Hooks Basic, ContextEditing & Database Tools|Tutorial Hooks: Basic, ContextEditing & Database Tools]]
- [[_COMMUNITY_Tutorial Models ChatModel Creation & Configuration|Tutorial Models: ChatModel Creation & Configuration]]
- [[_COMMUNITY_Advanced AsyncToolExecution Basic & Cancellable Async|Advanced AsyncToolExecution: Basic & Cancellable Async]]
- [[_COMMUNITY_Subgraph as StateGraph Isolated Subgraph Compilation|Subgraph as StateGraph: Isolated Subgraph Compilation]]
- [[_COMMUNITY_MCP Node Graph MCP Node Configuration & Application|MCP Node: Graph MCP Node Configuration & Application]]
- [[_COMMUNITY_Subgraph as CompiledGraph Compiled Node & Parent Graph|Subgraph as CompiledGraph: Compiled Node & Parent Graph]]
- [[_COMMUNITY_Advanced ContextEngineering StateAware & Personalized Prompts|Advanced ContextEngineering: StateAware & Personalized Prompts]]
- [[_COMMUNITY_A2A README Agent Config & Remote Agent Concepts|A2A README: Agent Config & Remote Agent Concepts]]
- [[_COMMUNITY_A2A README Auto-Config, Endpoints & Docker Runtime|A2A README: Auto-Config, Endpoints & Docker Runtime]]
- [[_COMMUNITY_Core Library Custom KeyStrategy & Conditional Edges|Core Library: Custom KeyStrategy & Conditional Edges]]
- [[_COMMUNITY_Core Persistence GetState, StateHistory & Persistence|Core Persistence: GetState, StateHistory & Persistence]]
- [[_COMMUNITY_A2A Controller Demo Runner & Example Endpoints|A2A Controller: Demo Runner & Example Endpoints]]
- [[_COMMUNITY_Graph Cancellation CancelWithForEachAsync & Iterator|Graph Cancellation: CancelWithForEachAsync & Iterator]]
- [[_COMMUNITY_README MCP Amap Maps, 12306 MCP & Graph MCP Node|README MCP: Amap Maps, 12306 MCP & Graph MCP Node]]
- [[_COMMUNITY_Graph WaitUserInput ContinueExecution & Interrupt|Graph WaitUserInput: ContinueExecution & Interrupt]]
- [[_COMMUNITY_Subgraph Example Compiled Subgraph & Stream Subgraph|Subgraph Example: Compiled Subgraph & Stream Subgraph]]
- [[_COMMUNITY_A2A Example AgentCardProvider & Demo Runner|A2A Example: AgentCardProvider & Demo Runner]]
- [[_COMMUNITY_A2A Application DemoRunner Main & CommandLineRunner|A2A Application: DemoRunner Main & CommandLineRunner]]
- [[_COMMUNITY_Long Running Task Error Recovery & Data Processing Node|Long Running Task: Error Recovery & Data Processing Node]]
- [[_COMMUNITY_README Config DashScope, Maven & Chat Model Setup|README Config: DashScope, Maven & Chat Model Setup]]
- [[_COMMUNITY_Graph PlantUML Generate PlantUML from StateGraph|Graph PlantUML: Generate PlantUML from StateGraph]]
- [[_COMMUNITY_MCP RemoteTools Application Bootstrap|MCP RemoteTools: Application Bootstrap]]
- [[_COMMUNITY_README Multi-Agent Supervisor & Multi-Agent Overview|README: Multi-Agent Supervisor & Multi-Agent Overview]]

## God Nodes (most connected - your core abstractions)
1. `Spring AI Alibaba 文档示例模块` - 38 edges
2. `String` - 29 edges
3. `MessagesExample` - 24 edges
4. `String` - 23 edges
5. `Override` - 20 edges
6. `ToolsExample` - 20 edges
7. `String` - 19 edges
8. `AgentsExample` - 18 edges
9. `HooksExample` - 17 edges
10. `String` - 16 edges

## Surprising Connections (you probably didn't know these)
- `Spring AI Alibaba 文档示例模块` --implements--> `McpNodeExample（MCP 节点集成）`  [INFERRED]
  examples/documentation/README.md → examples/documentation/src/main/java/com/alibaba/cloud/ai/examples/documentation/graph/examples/McpNodeExample.java
- `Spring AI Alibaba 文档示例模块` --implements--> `MultiAgentSupervisorExample（多智能体监督者模式）`  [INFERRED]
  examples/documentation/README.md → examples/documentation/src/main/java/com/alibaba/cloud/ai/examples/documentation/graph/examples/MultiAgentSupervisorExample.java
- `Spring AI Alibaba 文档示例模块` --implements--> `RemoteMcpToolsExample（MCP 远程工具调用示例）`  [INFERRED]
  examples/documentation/README.md → examples/documentation/src/main/java/com/alibaba/cloud/ai/examples/documentation/framework/tutorials/mcp/RemoteMcpToolsExample.java
- `Spring AI Alibaba 文档示例模块` --implements--> `AgentToolExample（智能体工具调用示例）`  [INFERRED]
  examples/documentation/README.md → examples/documentation/src/main/java/com/alibaba/cloud/ai/examples/documentation/framework/advanced/AgentToolExample.java
- `Spring AI Alibaba 文档示例模块` --implements--> `AsyncToolExecutionExample（异步工具执行示例）`  [INFERRED]
  examples/documentation/README.md → examples/documentation/src/main/java/com/alibaba/cloud/ai/examples/documentation/framework/advanced/AsyncToolExecutionExample.java

## Communities (45 total, 8 thin omitted)

### Community 0 - "Tutorial Agents: ReAct Hooks & Agent Commands"
Cohesion: 0.07
Nodes (30): AgentHook, Double, Exception, AgentCommand, CompletableFuture, HookPosition, List, Map (+22 more)

### Community 1 - "Tutorial MCP & Tools: ToolCallback & Remote Services"
Cohesion: 0.06
Nodes (26): ToolCallbackProvider, List, Override, String, Tool, ToolCallback, ToolContext, AccountInfoTool (+18 more)

### Community 2 - "Tutorial Structured Output: Entities & Type Mappings"
Cohesion: 0.06
Nodes (11): Entities, String, Integer, ReviewDetails, ContactInfo, Entities, ProductReview, ReviewDetails (+3 more)

### Community 3 - "Tutorial Hooks & Interceptors: Agent Lifecycle Management"
Cohesion: 0.11
Nodes (28): AgentCommand, CompletableFuture, HookPosition, List, Map, Message, ModelCallHandler, ModelRequest (+20 more)

### Community 4 - "Graph Checkpoint: Redis Saver & State Persistence"
Cohesion: 0.09
Nodes (17): CheckpointRedisExample, PersistenceExample, TimeTravelExample, TimeTravelRedisExample, StateGraph, String, Builder, CompiledGraph (+9 more)

### Community 5 - "Graph Quickstart: BugTracking & Intent Classification Nodes"
Cohesion: 0.13
Nodes (19): BugTrackingNode, ClassifyIntentNode, DraftResponseNode, EmailClassification, HumanReviewNode, Builder, ChatModel, CompiledGraph (+11 more)

### Community 6 - "Tutorial Memory: ChatModel & Agent Message History"
Cohesion: 0.12
Nodes (18): AgentCommand, ChatModel, List, Message, Override, RedissonClient, RunnableConfig, String (+10 more)

### Community 7 - "Multi-Agent Supervisor: CodeRequest & Coder/Reviewer Nodes"
Cohesion: 0.11
Nodes (18): CodeRequest, CodeRequest, CoderNode, CoderTool, MultiAgentSupervisorExample, ResearcherNode, SearchRequest, SearchTool (+10 more)

### Community 8 - "A2A Config: AgentLoader & Data Analysis Agent Beans"
Cohesion: 0.12
Nodes (16): A2AAgentConfig, AgentLoader, Bean, ChatModel, ReactAgent, Builder, ChatModel, List (+8 more)

### Community 9 - "Core Streaming: ProcessStreamingNode & State Graph"
Cohesion: 0.11
Nodes (15): AsyncNodeAction, ProcessStreamingNode, StreamingExample, StreamingNode, ParallelBranchExample, ParallelStreamingExample, Builder, Map (+7 more)

### Community 10 - "README Documentation: Module Overview & Feature Index"
Cohesion: 0.07
Nodes (31): AgentToolExample（智能体工具调用示例）, AsyncToolExecutionExample（异步工具执行示例）, ContextEngineeringExample（上下文工程示例）, Spring AI Alibaba 文档示例模块, CancellationExample（任务取消）, CheckpointRedisExample（Redis 检查点示例）, CoreLibraryExample（Graph 核心库示例）, LlmStreamingSpringAiExample（LLM 流式集成） (+23 more)

### Community 11 - "Human-in-the-Loop: ContinueExecution & Interrupt Patterns"
Cohesion: 0.17
Nodes (14): AsyncNodeActionWithConfig, HumanInTheLoopExample, InterruptableNodeAction, CompiledGraph, CompletableFuture, InterruptionMetadata, Map, Object (+6 more)

### Community 12 - "Advanced RAG: KnowledgeBase, TwoStep & Agentic RAG"
Cohesion: 0.10
Nodes (13): RAGExample, ChatClient, LlmStreamingSpringAiExample, StreamingAgentNode, ChatModel, String, Builder, Map (+5 more)

### Community 13 - "Advanced Workflow: Parallel Aggregator & Routing Agent"
Cohesion: 0.13
Nodes (9): ParallelResultAggregatorNode, WorkflowExample, FlowAgent, ChatModel, Map, Object, OverAllState, Override (+1 more)

### Community 14 - "Advanced Memory: Tool Read/Write & Model Hook Memory"
Cohesion: 0.12
Nodes (8): MemoryExample, MemoryExample, ChatModel, String, Builder, Object, String, MemoryStore

### Community 16 - "Advanced HumanInTheLoop: Approve/Edit/Tool Decisions"
Cohesion: 0.17
Nodes (6): HumanInTheLoopExample, MultiTools, ChatModel, InterruptionMetadata, String, Tool

### Community 17 - "Advanced Tool Selection: Optional Tools & OverallState"
Cohesion: 0.21
Nodes (7): Optional, OverAllState, String, Tool, ToolSelectionExample, TravelTools, UtilityTools

### Community 18 - "Agent as Tool: AgentToolExample with Input Schema"
Cohesion: 0.16
Nodes (4): AgentToolExample, ArticleOutput, ChatModel, String

### Community 19 - "Advanced Multi-Agent: Sequential/Parallel & Custom Merge"
Cohesion: 0.19
Nodes (4): MultiAgentExample, ChatModel, String, SequentialAgent

### Community 20 - "Subgraph as NodeAction: Subgraph Compilation & Execution"
Cohesion: 0.22
Nodes (10): ConfigurableSubGraphNode, SubgraphAsNodeActionExample, SubGraphNode, CompiledGraph, KeyStrategyFactory, Map, Object, OverAllState (+2 more)

### Community 24 - "Advanced AsyncToolExecution: Basic & Cancellable Async"
Cohesion: 0.23
Nodes (4): AsyncToolExecutionExample, AsyncToolCallback, ChatModel, String

### Community 25 - "Subgraph as StateGraph: Isolated Subgraph Compilation"
Cohesion: 0.24
Nodes (8): IsolatedSubGraphNode, SubgraphAsStateGraphExample, Map, Object, OverAllState, Override, StateGraph, String

### Community 26 - "MCP Node: Graph MCP Node Configuration & Application"
Cohesion: 0.21
Nodes (10): McpNode, McpNodeExample, Builder, Map, Object, OverAllState, Override, String (+2 more)

### Community 27 - "Subgraph as CompiledGraph: Compiled Node & Parent Graph"
Cohesion: 0.23
Nodes (8): CompiledSubGraphNode, SubgraphAsCompiledGraphExample, CompiledGraph, Map, Object, OverAllState, Override, String

### Community 28 - "Advanced ContextEngineering: StateAware & Personalized Prompts"
Cohesion: 0.26
Nodes (3): ContextEngineeringExample, ChatModel, String

### Community 29 - "A2A README: Agent Config & Remote Agent Concepts"
Cohesion: 0.31
Nodes (11): A2AAgentConfig（ReactAgent Bean 定义）, Agent-to-Agent（A2A）通信协议, A2AExample（A2A 一体化演示入口）, A2AExampleController（/api/a2a/demo 端点）, A2aRemoteAgent（远程 A2A 代理调用）, A2A Server（Agent-to-Agent 服务端）, AgentCardProvider（智能体卡片配置）, data_analysis_agent（数据分析智能体） (+3 more)

### Community 30 - "A2A README: Auto-Config, Endpoints & Docker Runtime"
Cohesion: 0.20
Nodes (11): A2A Server AutoConfiguration（自动配置）, /a2a/message REST 端点, AgentCard（智能体元数据卡片）, agent-endpoints Nacos 服务分组, Docker 容器运行时, Nacos A2A Discovery（服务发现）, Nacos A2A Registry（服务注册）, Nacos Server（服务注册中心） (+3 more)

### Community 31 - "Core Library: Custom KeyStrategy & Conditional Edges"
Cohesion: 0.38
Nodes (3): CoreLibraryExample, KeyStrategyFactory, String

### Community 32 - "Core Persistence: GetState, StateHistory & Persistence"
Cohesion: 0.38
Nodes (3): PersistenceExample, CompiledGraph, String

### Community 33 - "A2A Controller: Demo Runner & Example Endpoints"
Cohesion: 0.27
Nodes (7): A2AExampleController, A2AExample, Autowired, Map, Object, String, GetMapping

### Community 34 - "Graph Cancellation: CancelWithForEachAsync & Iterator"
Cohesion: 0.31
Nodes (4): Disposable, CancellationExample, CompiledGraph, String

### Community 35 - "README MCP: Amap Maps, 12306 MCP & Graph MCP Node"
Cohesion: 0.31
Nodes (9): 12306-mcp MCP 工具（火车票查询）, amap-maps MCP 工具（高德地图）, McpNodeExample（MCP 节点集成）, Spring AI MCP Client, RemoteMcpToolsApplication（MCP 教程应用）, RemoteMcpToolsExample（MCP 远程工具调用示例）, ModelScope 魔搭社区 MCP 推理端点, MCP SSE 传输协议 (+1 more)

### Community 36 - "Graph WaitUserInput: ContinueExecution & Interrupt"
Cohesion: 0.44
Nodes (3): WaitUserInputExample, CompiledGraph, String

### Community 38 - "A2A Example: AgentCardProvider & Demo Runner"
Cohesion: 0.43
Nodes (5): A2AExample, AgentCardProvider, Autowired, ChatModel, ReactAgent

### Community 39 - "A2A Application: DemoRunner Main & CommandLineRunner"
Cohesion: 0.33
Nodes (4): DocumentationApplication, CommandLineRunner, A2AExample, String

### Community 40 - "Long Running Task: Error Recovery & Data Processing Node"
Cohesion: 0.38
Nodes (3): LongTimeRunningTaskExample, CompiledGraph, String

### Community 41 - "README Config: DashScope, Maven & Chat Model Setup"
Cohesion: 0.33
Nodes (6): ChatModel（Spring AI 对话模型接口）, DASHSCOPE_API_KEY 环境变量, DashScope（阿里云百炼）LLM 提供商, documentation-examples Spring Boot 应用, Maven 构建系统, qwen-plus 模型

## Knowledge Gaps
- **73 isolated node(s):** `String`, `String`, `Exception`, `WeatherRequest`, `WeatherResponse` (+68 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **8 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `ChatClient` connect `Advanced RAG: KnowledgeBase, TwoStep & Agentic RAG` to `Graph Checkpoint: Redis Saver & State Persistence`, `Graph Quickstart: BugTracking & Intent Classification Nodes`, `Multi-Agent Supervisor: CodeRequest & Coder/Reviewer Nodes`, `A2A Config: AgentLoader & Data Analysis Agent Beans`, `Core Streaming: ProcessStreamingNode & State Graph`, `Advanced Workflow: Parallel Aggregator & Routing Agent`, `Advanced Memory: Tool Read/Write & Model Hook Memory`, `MCP Node: Graph MCP Node Configuration & Application`?**
  _High betweenness centrality (0.174) - this node is a cross-community bridge._
- **Are the 36 inferred relationships involving `Spring AI Alibaba 文档示例模块` (e.g. with `A2AExample（A2A 一体化演示入口）` and `AgentToolExample（智能体工具调用示例）`) actually correct?**
  _`Spring AI Alibaba 文档示例模块` has 36 INFERRED edges - model-reasoned connections that need verification._
- **What connects `String`, `String`, `Exception` to the rest of the system?**
  _73 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Tutorial Agents: ReAct Hooks & Agent Commands` be split into smaller, more focused modules?**
  _Cohesion score 0.06826923076923076 - nodes in this community are weakly interconnected._
- **Should `Tutorial MCP & Tools: ToolCallback & Remote Services` be split into smaller, more focused modules?**
  _Cohesion score 0.05961538461538462 - nodes in this community are weakly interconnected._
- **Should `Tutorial Structured Output: Entities & Type Mappings` be split into smaller, more focused modules?**
  _Cohesion score 0.05875706214689266 - nodes in this community are weakly interconnected._
- **Should `Tutorial Hooks & Interceptors: Agent Lifecycle Management` be split into smaller, more focused modules?**
  _Cohesion score 0.11224489795918367 - nodes in this community are weakly interconnected._