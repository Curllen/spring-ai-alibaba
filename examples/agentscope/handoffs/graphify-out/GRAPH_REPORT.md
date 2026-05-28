# Graph Report - /workspace/examples/agentscope/handoffs  (2026-05-28)

## Corpus Check
- Corpus is ~3,323 words - fits in a single context window. You may not need a graph.

## Summary
- 117 nodes · 160 edges · 12 communities (11 shown, 1 thin omitted)
- Extraction: 99% EXTRACTED · 1% INFERRED · 0% AMBIGUOUS · INFERRED: 2 edges (avg confidence: 0.7)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_README Documentation & Configuration Concepts|README Documentation & Configuration Concepts]]
- [[_COMMUNITY_AgentScope Handoffs Config & Agent Beans|AgentScope Handoffs Config & Agent Beans]]
- [[_COMMUNITY_Update Extra State Tool & State Management|Update Extra State Tool & State Management]]
- [[_COMMUNITY_AgentScope Application Bootstrap & Listener|AgentScope Application Bootstrap & Listener]]
- [[_COMMUNITY_Route After Sales Action & Async Command|Route After Sales Action & Async Command]]
- [[_COMMUNITY_Transfer To Support Agent Handoff Tool|Transfer To Support Agent Handoff Tool]]
- [[_COMMUNITY_AgentScope Handoffs Runner & CLI Entry|AgentScope Handoffs Runner & CLI Entry]]
- [[_COMMUNITY_Route After Support Action & Async Command|Route After Support Action & Async Command]]
- [[_COMMUNITY_Route Initial Action & Graph Entry Point|Route Initial Action & Graph Entry Point]]
- [[_COMMUNITY_Transfer To Sales Agent Handoff Tool|Transfer To Sales Agent Handoff Tool]]
- [[_COMMUNITY_AgentScope Handoffs Service & Graph Execution|AgentScope Handoffs Service & Graph Execution]]
- [[_COMMUNITY_AgentScope State Constants & Keys|AgentScope State Constants & Keys]]

## God Nodes (most connected - your core abstractions)
1. `StateGraph (LangGraph)` - 7 edges
2. `Support Agent (AgentScope ReActAgent)` - 6 edges
3. `AgentScopeHandoffsConfig` - 5 edges
4. `Bean` - 5 edges
5. `UpdateExtraStateTool` - 5 edges
6. `active_agent State Key` - 5 edges
7. `AgentScopeHandoffsRunner` - 4 edges
8. `TransferToSupportTool` - 4 edges
9. `TransferToSalesTool` - 4 edges
10. `Sales Agent (Spring AI ReactAgent)` - 4 edges

## Surprising Connections (you probably didn't know these)
- `agentscope.runner.enabled` --references--> `Multiple Agent Subgraphs Handoffs Pattern`  [EXTRACTED]
  examples/agentscope/handoffs/src/main/resources/application.yml → examples/agentscope/handoffs/README.md
- `spring.ai.dashscope.api-key` --references--> `DashScope API`  [EXTRACTED]
  examples/agentscope/handoffs/src/main/resources/application.yml → examples/agentscope/handoffs/README.md

## Hyperedges (group relationships)
- **Agent Handoff State Management via active_agent, ToolContext, and Conditional Routing** — readme_active_agent, readme_tool_context, readme_conditional_routing [EXTRACTED 1.00]
- **AgentScope Integration: Support Agent, Toolkit, and ReActAgent** — readme_support_agent, readme_agentscope_toolkit, readme_react_agent [EXTRACTED 1.00]
- **Spring Configuration Cross-Reference: application.yml, DashScope API Key, and Runner** — config_application_yml, config_dashscope_api_key, config_agentscope_runner_enabled [EXTRACTED 1.00]

## Communities (12 total, 1 thin omitted)

### Community 0 - "README Documentation & Configuration Concepts"
Cohesion: 0.11
Nodes (25): agentscope.runner.enabled, application.yml (AgentScope Handoffs), spring.ai.dashscope.api-key, Server Port 8089, active_agent State Key, Multiple Agent Subgraphs Handoffs Pattern, AgentScopeHandoffsConfig, AgentScopeHandoffsService (+17 more)

### Community 1 - "AgentScope Handoffs Config & Agent Beans"
Cohesion: 0.29
Nodes (8): AgentScopeHandoffsConfig, AgentScopeAgent, AgentScopeHandoffsService, Bean, CompiledGraph, String, ChatModel, ReactAgent

### Community 2 - "Update Extra State Tool & State Management"
Cohesion: 0.31
Nodes (5): OverAllState, String, Tool, ToolContext, UpdateExtraStateTool

### Community 3 - "AgentScope Application Bootstrap & Listener"
Cohesion: 0.33
Nodes (6): AgentScopeApplication, Bean, String, ApplicationListener, ApplicationReadyEvent, Environment

### Community 4 - "Route After Sales Action & Async Command"
Cohesion: 0.36
Nodes (7): AsyncCommandAction, Command, CompletableFuture, OverAllState, Override, RunnableConfig, RouteAfterSalesAction

### Community 5 - "Transfer To Support Agent Handoff Tool"
Cohesion: 0.31
Nodes (5): ToolCallback, String, Tool, ToolContext, TransferToSupportTool

### Community 6 - "AgentScope Handoffs Runner & CLI Entry"
Cohesion: 0.32
Nodes (5): AgentScopeHandoffsRunner, AgentScopeHandoffsService, Override, ApplicationArguments, ApplicationRunner

### Community 7 - "Route After Support Action & Async Command"
Cohesion: 0.39
Nodes (6): Command, CompletableFuture, OverAllState, Override, RunnableConfig, RouteAfterSupportAction

### Community 8 - "Route Initial Action & Graph Entry Point"
Cohesion: 0.39
Nodes (6): Command, CompletableFuture, OverAllState, Override, RunnableConfig, RouteInitialAction

### Community 9 - "Transfer To Sales Agent Handoff Tool"
Cohesion: 0.32
Nodes (4): String, Tool, ToolContext, TransferToSalesTool

### Community 10 - "AgentScope Handoffs Service & Graph Execution"
Cohesion: 0.33
Nodes (4): AgentScopeHandoffsService, AgentScopeHandoffsResult, CompiledGraph, String

## Knowledge Gaps
- **18 isolated node(s):** `String`, `String`, `AgentScopeHandoffsService`, `String`, `AgentScopeHandoffsResult` (+13 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **What connects `String`, `String`, `AgentScopeHandoffsService` to the rest of the system?**
  _18 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `README Documentation & Configuration Concepts` be split into smaller, more focused modules?**
  _Cohesion score 0.11333333333333333 - nodes in this community are weakly interconnected._