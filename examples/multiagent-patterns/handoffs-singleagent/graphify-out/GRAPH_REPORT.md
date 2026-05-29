# Graph Report - /workspace/examples/multiagent-patterns/handoffs-singleagent  (2026-05-29)

## Corpus Check
- Corpus is ~2,966 words - fits in a single context window. You may not need a graph.

## Summary
- 109 nodes · 179 edges · 13 communities (9 shown, 4 thin omitted)
- Extraction: 95% EXTRACTED · 5% INFERRED · 0% AMBIGUOUS · INFERRED: 9 edges (avg confidence: 0.8)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_SupportTools All Tool Definitions (Warranty, Issue, Solution, Escalation)|SupportTools: All Tool Definitions (Warranty, Issue, Solution, Escalation)]]
- [[_COMMUNITY_StepConfigInterceptor Step-Based Model Interception & Prompt Routing|StepConfigInterceptor: Step-Based Model Interception & Prompt Routing]]
- [[_COMMUNITY_AgentStaticLoader Studio Agent Discovery & Loading|AgentStaticLoader: Studio Agent Discovery & Loading]]
- [[_COMMUNITY_Handoffs Workflow Steps & Tools Semantic Architecture|Handoffs Workflow Steps & Tools: Semantic Architecture]]
- [[_COMMUNITY_HandoffsSupportHook State Key Strategies & Model Hook|HandoffsSupportHook: State Key Strategies & Model Hook]]
- [[_COMMUNITY_Agent Configuration & Runtime Config, Hook, Saver, State Keys|Agent Configuration & Runtime: Config, Hook, Saver, State Keys]]
- [[_COMMUNITY_HandoffsApplication Boot Entry Point & Lifecycle|HandoffsApplication: Boot Entry Point & Lifecycle]]
- [[_COMMUNITY_HandoffsRunner Four-Turn Demo Execution|HandoffsRunner: Four-Turn Demo Execution]]
- [[_COMMUNITY_HandoffsConfig supportAgent Bean Assembly & MemorySaver|HandoffsConfig: supportAgent Bean Assembly & MemorySaver]]
- [[_COMMUNITY_SupportStateConstants State Key Definitions|SupportStateConstants: State Key Definitions]]
- [[_COMMUNITY_Handoffs Single-Agent Module Overview|Handoffs Single-Agent Module Overview]]
- [[_COMMUNITY_DashScope API Configuration|DashScope API Configuration]]
- [[_COMMUNITY_SupportStateConstants Documentation Reference|SupportStateConstants Documentation Reference]]

## God Nodes (most connected - your core abstractions)
1. `SupportTools` - 12 edges
2. `ToolCallback` - 10 edges
3. `StepConfigInterceptor` - 6 edges
4. `HandoffsSupportHook` - 6 edges
5. `AgentStaticLoader` - 5 edges
6. `String` - 5 edges
7. `ToolContext` - 5 edges
8. `Tool` - 5 edges
9. `ReactAgent (supportAgent)` - 5 edges
10. `StepConfigInterceptor (ModelInterceptor)` - 5 edges

## Surprising Connections (you probably didn't know these)
- `StepConfigInterceptor` --inherits--> `ModelInterceptor`  [EXTRACTED]
  support/StepConfigInterceptor.java → support/HandoffsSupportHook.java
- `handoffs.run-examples (Demo Toggle)` --references--> `HandoffsRunner (Demo Runner)`  [EXTRACTED]
  examples/multiagent-patterns/handoffs-singleagent/src/main/resources/application.yml → examples/multiagent-patterns/handoffs-singleagent/README.md

## Hyperedges (group relationships)
- **Handoffs Workflow Pipeline (warranty_collector -> issue_classifier -> resolution_specialist)** — README_step_warranty_collector, README_step_issue_classifier, README_step_resolution_specialist [EXTRACTED 1.00]
- **Graph State Variables (current_step, warranty_status, issue_type)** — README_statekey_current_step, README_statekey_warranty_status, README_statekey_issue_type [EXTRACTED 1.00]
- **Agent Architecture: ReactAgent + StepConfigInterceptor + Hook** — README_reactagent, README_stepconfiginterceptor, README_handoffssupporthook [EXTRACTED 1.00]
- **State-Updating Tools (record_warranty_status, record_issue_type)** — README_tool_record_warranty_status, README_tool_record_issue_type, README_toolcontexthelper [EXTRACTED 1.00]

## Communities (13 total, 4 thin omitted)

### Community 0 - "SupportTools: All Tool Definitions (Warranty, Issue, Solution, Escalation)"
Cohesion: 0.26
Nodes (6): Tool, ToolCallback, ToolContext, List, String, SupportTools

### Community 1 - "StepConfigInterceptor: Step-Based Model Interception & Prompt Routing"
Cohesion: 0.23
Nodes (10): ModelCallHandler, ModelRequest, ModelResponse, Object, StepConfig, ModelInterceptor, Map, Override (+2 more)

### Community 2 - "AgentStaticLoader: Studio Agent Discovery & Loading"
Cohesion: 0.27
Nodes (8): Agent, AgentLoader, List, Override, ReactAgent, String, Nonnull, AgentStaticLoader

### Community 3 - "Handoffs Workflow Steps & Tools: Semantic Architecture"
Cohesion: 0.29
Nodes (11): State Key: current_step, Step: issue_classifier, Step: resolution_specialist, Step: warranty_collector, StepConfigInterceptor (ModelInterceptor), SupportTools, Tool: escalate_to_human, Tool: provide_solution (+3 more)

### Community 4 - "HandoffsSupportHook: State Key Strategies & Model Hook"
Cohesion: 0.31
Nodes (7): KeyStrategy, ModelHook, HandoffsSupportHook, List, Map, Override, String

### Community 5 - "Agent Configuration & Runtime: Config, Hook, Saver, State Keys"
Cohesion: 0.22
Nodes (10): HandoffsConfig, HandoffsRunner (Demo Runner), HandoffsSupportHook, MemorySaver (Checkpointer), ReactAgent (supportAgent), ReplaceStrategy (Key Merge Strategy), RunnableConfig (thread_id), State Key: issue_type (+2 more)

### Community 6 - "HandoffsApplication: Boot Entry Point & Lifecycle"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, Environment, Bean, String, HandoffsApplication

### Community 7 - "HandoffsRunner: Four-Turn Demo Execution"
Cohesion: 0.36
Nodes (5): ApplicationArguments, ApplicationRunner, Override, ReactAgent, HandoffsRunner

### Community 8 - "HandoffsConfig: supportAgent Bean Assembly & MemorySaver"
Cohesion: 0.46
Nodes (5): ChatModel, Bean, ReactAgent, MemorySaver, HandoffsConfig

## Knowledge Gaps
- **12 isolated node(s):** `Override`, `String`, `StepConfig`, `Object`, `Handoffs Single-Agent Module` (+7 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **4 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `ToolCallback` connect `SupportTools: All Tool Definitions (Warranty, Issue, Solution, Escalation)` to `HandoffsConfig: supportAgent Bean Assembly & MemorySaver`, `StepConfigInterceptor: Step-Based Model Interception & Prompt Routing`, `HandoffsSupportHook: State Key Strategies & Model Hook`?**
  _High betweenness centrality (0.111) - this node is a cross-community bridge._
- **What connects `Override`, `String`, `StepConfig` to the rest of the system?**
  _12 weakly-connected nodes found - possible documentation gaps or missing edges._