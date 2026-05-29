# Graph Report - /workspace/examples/multiagent-patterns/handoffs-multiagent  (2026-05-29)

## Corpus Check
- Corpus is ~2,689 words - fits in a single context window. You may not need a graph.

## Summary
- 101 nodes · 145 edges · 12 communities (9 shown, 3 thin omitted)
- Extraction: 94% EXTRACTED · 5% INFERRED · 1% AMBIGUOUS · INFERRED: 7 edges (avg confidence: 0.91)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Initial & After-Support Route Actions StateGraph Conditional Edges|Initial & After-Support Route Actions: StateGraph Conditional Edges]]
- [[_COMMUNITY_Handoffs Multi-Agent Architecture StateGraph & Agent Routing|Handoffs Multi-Agent Architecture: StateGraph & Agent Routing]]
- [[_COMMUNITY_MultiAgentHandoffsConfig Agent Bean Definition & Graph Wiring|MultiAgentHandoffsConfig: Agent Bean Definition & Graph Wiring]]
- [[_COMMUNITY_HandoffsApplication Boot Entry Point & Lifecycle|HandoffsApplication: Boot Entry Point & Lifecycle]]
- [[_COMMUNITY_TransferToSalesTool Sales Handoff Implementation|TransferToSalesTool: Sales Handoff Implementation]]
- [[_COMMUNITY_TransferToSupportTool Support Handoff Implementation|TransferToSupportTool: Support Handoff Implementation]]
- [[_COMMUNITY_MultiAgentHandoffsRunner Demo Runner Execution|MultiAgentHandoffsRunner: Demo Runner Execution]]
- [[_COMMUNITY_RouteAfterSalesAction Sales→SupportEND Routing|RouteAfterSalesAction: Sales→Support/END Routing]]
- [[_COMMUNITY_MultiAgentHandoffsService Graph Invocation & Results|MultiAgentHandoffsService: Graph Invocation & Results]]
- [[_COMMUNITY_MultiAgentStateConstants Agent State Definitions|MultiAgentStateConstants: Agent State Definitions]]
- [[_COMMUNITY_DashScope API Configuration & Module Overview|DashScope API Configuration & Module Overview]]
- [[_COMMUNITY_Built-in Chat UI Interface|Built-in Chat UI Interface]]

## God Nodes (most connected - your core abstractions)
1. `Active Agent State Field` - 8 edges
2. `Parent StateGraph` - 7 edges
3. `MultiAgentHandoffsConfig` - 5 edges
4. `Bean` - 5 edges
5. `Sales Agent Node` - 5 edges
6. `Support Agent Node` - 5 edges
7. `TransferToSalesTool` - 5 edges
8. `TransferToSupportTool` - 5 edges
9. `returnDirect=true Pattern` - 5 edges
10. `ReactAgent` - 4 edges

## Surprising Connections (you probably didn't know these)
- `Full Message History Context` --shares_data_with--> `Active Agent State Field`  [INFERRED]
  examples/multiagent-patterns/handoffs-multiagent/README.md → examples/multiagent-patterns/handoffs-multiagent/src/main/java/.../handoffs/state/MultiAgentStateConstants.java
- `returnDirect=true Pattern` --conceptually_related_to--> `RouteAfterSalesAction`  [AMBIGUOUS]
  examples/multiagent-patterns/handoffs-multiagent/README.md → examples/multiagent-patterns/handoffs-multiagent/src/main/java/.../handoffs/route/RouteAfterSalesAction.java
- `returnDirect=true Pattern` --conceptually_related_to--> `RouteAfterSupportAction`  [AMBIGUOUS]
  examples/multiagent-patterns/handoffs-multiagent/README.md → examples/multiagent-patterns/handoffs-multiagent/src/main/java/.../handoffs/route/RouteAfterSupportAction.java
- `Sales Agent Node` --implements--> `ReactAgent (CompiledGraph)`  [EXTRACTED]
  examples/multiagent-patterns/handoffs-multiagent/src/main/java/.../handoffs/MultiAgentHandoffsConfig.java → examples/multiagent-patterns/handoffs-multiagent/README.md
- `Studio Agent Auto-Discovery` --references--> `Sales Agent Node`  [EXTRACTED]
  examples/multiagent-patterns/handoffs-multiagent/README.md → examples/multiagent-patterns/handoffs-multiagent/src/main/java/.../handoffs/MultiAgentHandoffsConfig.java

## Hyperedges (group relationships)
- **Support→Sales Handoff Flow** — transfer_to_sales_tool, active_agent, support_agent [EXTRACTED 1.00]
- **Sales→Support Handoff Flow** — transfer_to_support_tool, active_agent, sales_agent [EXTRACTED 1.00]
- **StateGraph Conditional Routing** — state_graph, route_initial, route_after_sales [EXTRACTED 1.00]

## Communities (12 total, 3 thin omitted)

### Community 0 - "Initial & After-Support Route Actions: StateGraph Conditional Edges"
Cohesion: 0.19
Nodes (13): AsyncCommandAction, Command, CompletableFuture, OverAllState, Override, RunnableConfig, RouteAfterSupportAction, Command (+5 more)

### Community 1 - "Handoffs Multi-Agent Architecture: StateGraph & Agent Routing"
Cohesion: 0.24
Nodes (17): Active Agent State Field, Demo Runner (handoffs.runner.enabled), Full Message History Context, MultiAgentHandoffsConfig, MultiAgentHandoffsService, ReactAgent (CompiledGraph), returnDirect=true Pattern, RouteAfterSalesAction (+9 more)

### Community 2 - "MultiAgentHandoffsConfig: Agent Bean Definition & Graph Wiring"
Cohesion: 0.38
Nodes (6): ChatModel, MultiAgentHandoffsConfig, Bean, CompiledGraph, MultiAgentHandoffsService, ReactAgent

### Community 3 - "HandoffsApplication: Boot Entry Point & Lifecycle"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, Environment, HandoffsApplication, Bean, String

### Community 4 - "TransferToSalesTool: Sales Handoff Implementation"
Cohesion: 0.31
Nodes (5): String, Tool, ToolCallback, ToolContext, TransferToSalesTool

### Community 5 - "TransferToSupportTool: Support Handoff Implementation"
Cohesion: 0.31
Nodes (5): String, Tool, ToolCallback, ToolContext, TransferToSupportTool

### Community 6 - "MultiAgentHandoffsRunner: Demo Runner Execution"
Cohesion: 0.32
Nodes (5): ApplicationArguments, ApplicationRunner, MultiAgentHandoffsRunner, MultiAgentHandoffsService, Override

### Community 7 - "RouteAfterSalesAction: Sales→Support/END Routing"
Cohesion: 0.39
Nodes (6): Command, CompletableFuture, OverAllState, Override, RunnableConfig, RouteAfterSalesAction

### Community 8 - "MultiAgentHandoffsService: Graph Invocation & Results"
Cohesion: 0.33
Nodes (4): MultiAgentHandoffsService, MultiAgentHandoffsResult, CompiledGraph, String

## Ambiguous Edges - Review These
- `returnDirect=true Pattern` → `RouteAfterSalesAction`  [AMBIGUOUS]
  examples/multiagent-patterns/handoffs-multiagent/README.md · relation: conceptually_related_to
- `returnDirect=true Pattern` → `RouteAfterSupportAction`  [AMBIGUOUS]
  examples/multiagent-patterns/handoffs-multiagent/README.md · relation: conceptually_related_to

## Knowledge Gaps
- **16 isolated node(s):** `String`, `MultiAgentHandoffsResult`, `MultiAgentHandoffsService`, `String`, `MultiAgentHandoffsService` (+11 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **3 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **What is the exact relationship between `returnDirect=true Pattern` and `RouteAfterSalesAction`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **What is the exact relationship between `returnDirect=true Pattern` and `RouteAfterSupportAction`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **Why does `RouteAfterSalesAction` connect `RouteAfterSalesAction: Sales→Support/END Routing` to `Initial & After-Support Route Actions: StateGraph Conditional Edges`?**
  _High betweenness centrality (0.007) - this node is a cross-community bridge._
- **Are the 4 inferred relationships involving `Active Agent State Field` (e.g. with `Full Message History Context` and `RouteAfterSalesAction`) actually correct?**
  _`Active Agent State Field` has 4 INFERRED edges - model-reasoned connections that need verification._
- **What connects `String`, `MultiAgentHandoffsResult`, `MultiAgentHandoffsService` to the rest of the system?**
  _16 weakly-connected nodes found - possible documentation gaps or missing edges._