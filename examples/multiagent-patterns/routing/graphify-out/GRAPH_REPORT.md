# Graph Report - /workspace/examples/multiagent-patterns/routing  (2026-05-29)

## Corpus Check
- Corpus is ~6,217 words - fits in a single context window. You may not need a graph.

## Summary
- 191 nodes · 299 edges · 19 communities
- Extraction: 97% EXTRACTED · 3% INFERRED · 0% AMBIGUOUS · INFERRED: 8 edges (avg confidence: 0.81)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Routing Architecture LlmRoutingAgent & Two Patterns (SimpleGraph)|Routing Architecture: LlmRoutingAgent & Two Patterns (Simple/Graph)]]
- [[_COMMUNITY_RouterService LlmRoutingAgent Invocation & State Management|RouterService: LlmRoutingAgent Invocation & State Management]]
- [[_COMMUNITY_Graph Nodes PreprocessNode & PostprocessNode Pipeline|Graph Nodes: PreprocessNode & PostprocessNode Pipeline]]
- [[_COMMUNITY_RoutingGraphConfig StateGraph Bean Assembly & Subgraph Nodes|RoutingGraphConfig: StateGraph Bean Assembly & Subgraph Nodes]]
- [[_COMMUNITY_Routing Runners Simple & Graph Demo Execution|Routing Runners: Simple & Graph Demo Execution]]
- [[_COMMUNITY_RoutingConfig Simple Agent Beans & RouterService Assembly|RoutingConfig: Simple Agent Beans & RouterService Assembly]]
- [[_COMMUNITY_Graph AgentStaticLoader LlmRoutingAgent Discovery & Loading|Graph AgentStaticLoader: LlmRoutingAgent Discovery & Loading]]
- [[_COMMUNITY_Simple AgentStaticLoader LlmRoutingAgent Discovery & Loading|Simple AgentStaticLoader: LlmRoutingAgent Discovery & Loading]]
- [[_COMMUNITY_RoutingGraphApplication Graph Boot Entry & Lifecycle|RoutingGraphApplication: Graph Boot Entry & Lifecycle]]
- [[_COMMUNITY_RoutingApplication Simple Boot Entry & Lifecycle|RoutingApplication: Simple Boot Entry & Lifecycle]]
- [[_COMMUNITY_RoutingGraphService CompiledGraph Invocation & Results|RoutingGraphService: CompiledGraph Invocation & Results]]
- [[_COMMUNITY_Graph GitHubStubTools search_codeissuepr Tools|Graph GitHubStubTools: search_code/issue/pr Tools]]
- [[_COMMUNITY_Simple GitHubStubTools search_codeissuepr Tools|Simple GitHubStubTools: search_code/issue/pr Tools]]
- [[_COMMUNITY_Graph NotionStubTools search_notionget_page Tools|Graph NotionStubTools: search_notion/get_page Tools]]
- [[_COMMUNITY_Graph SlackStubTools search_slackget_thread Tools|Graph SlackStubTools: search_slack/get_thread Tools]]
- [[_COMMUNITY_Simple NotionStubTools search_notionget_page Tools|Simple NotionStubTools: search_notion/get_page Tools]]
- [[_COMMUNITY_Simple SlackStubTools search_slackget_thread Tools|Simple SlackStubTools: search_slack/get_thread Tools]]

## God Nodes (most connected - your core abstractions)
1. `LlmRoutingAgent: LLM-Based Query Router` - 9 edges
2. `RouterService` - 8 edges
3. `RoutingGraphConfig` - 7 edges
4. `Bean` - 7 edges
5. `RoutingConfig` - 6 edges
6. `ChatModel` - 6 edges
7. `Bean` - 6 edges
8. `Simple Routing Pattern: Classify->Parallel->Synthesize` - 6 edges
9. `StateGraph (Graph Routing Backbone)` - 6 edges
10. `AgentStaticLoader` - 5 edges

## Surprising Connections (you probably didn't know these)
- `Simple Routing Pattern: Classify->Parallel->Synthesize` --semantically_similar_to--> `Graph Routing Pattern: StateGraph with LlmRoutingAgent Subgraph`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/routing/simple/README.md → examples/multiagent-patterns/routing/graph/README.md
- `RouterService: LlmRoutingAgent Wrapper + Synthesis` --semantically_similar_to--> `RoutingMergeNode: LLM-Based Sub-Agent Output Synthesis`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/routing/simple/README.md → examples/multiagent-patterns/routing/graph/README.md
- `Simple Routing Pattern: Classify->Parallel->Synthesize` --references--> `DashScope API (AI Provider)`  [EXTRACTED]
  examples/multiagent-patterns/routing/simple/README.md → examples/multiagent-patterns/routing/src/main/resources/application.yml
- `LlmRoutingAgent: LLM-Based Query Router` --references--> `RoutingMergeNode: LLM-Based Sub-Agent Output Synthesis`  [EXTRACTED]
  examples/multiagent-patterns/routing/simple/README.md → examples/multiagent-patterns/routing/graph/README.md
- `Graph Routing Pattern: StateGraph with LlmRoutingAgent Subgraph` --references--> `LlmRoutingAgent: LLM-Based Query Router`  [EXTRACTED]
  examples/multiagent-patterns/routing/graph/README.md → examples/multiagent-patterns/routing/simple/README.md

## Hyperedges (group relationships)
- **Graph Routing Pipeline: Preprocess->Routing->Postprocess** — n5, n1, n6 [EXTRACTED 1.00]
- **Three Specialist Agents: GitHub/Notion/Slack** — n9, n10, n11 [EXTRACTED 1.00]
- **Simple Routing State Types: Classification+AgentOutput->RouterResult** — n12, n13, n14 [EXTRACTED 1.00]

## Communities (19 total, 0 thin omitted)

### Community 0 - "Routing Architecture: LlmRoutingAgent & Two Patterns (Simple/Graph)"
Cohesion: 0.15
Nodes (21): LlmRoutingAgent: LLM-Based Query Router, NotionAgent: search_notion/get_page, SlackAgent: search_slack/get_thread, Classification State Type (source, query), AgentOutput State Type (source, result), RouterResult: query+classifications+results+finalAnswer, StubTools (@Tool/@ToolParam Annotations), DashScope API (AI Provider) (+13 more)

### Community 1 - "RouterService: LlmRoutingAgent Invocation & State Management"
Cohesion: 0.24
Nodes (10): AgentOutput, Classification, RouterResult, ChatModel, List, LlmRoutingAgent, Object, OverAllState (+2 more)

### Community 2 - "Graph Nodes: PreprocessNode & PostprocessNode Pipeline"
Cohesion: 0.16
Nodes (13): Map, Object, OverAllState, Override, String, Map, Object, OverAllState (+5 more)

### Community 3 - "RoutingGraphConfig: StateGraph Bean Assembly & Subgraph Nodes"
Cohesion: 0.27
Nodes (10): Bean, ChatModel, CompiledGraph, GitHubStubTools, LlmRoutingAgent, NotionStubTools, ReactAgent, RoutingGraphService (+2 more)

### Community 4 - "Routing Runners: Simple & Graph Demo Execution"
Cohesion: 0.17
Nodes (9): ApplicationRunner, ApplicationArguments, Override, RoutingGraphService, RoutingGraphRunner, ApplicationArguments, Override, RouterService (+1 more)

### Community 5 - "RoutingConfig: Simple Agent Beans & RouterService Assembly"
Cohesion: 0.31
Nodes (9): Bean, ChatModel, GitHubStubTools, LlmRoutingAgent, NotionStubTools, ReactAgent, RouterService, SlackStubTools (+1 more)

### Community 6 - "Graph AgentStaticLoader: LlmRoutingAgent Discovery & Loading"
Cohesion: 0.27
Nodes (8): AgentLoader, AgentStaticLoader, Agent, List, LlmRoutingAgent, Nonnull, Override, String

### Community 7 - "Simple AgentStaticLoader: LlmRoutingAgent Discovery & Loading"
Cohesion: 0.29
Nodes (7): AgentStaticLoader, Agent, List, LlmRoutingAgent, Nonnull, Override, String

### Community 8 - "RoutingGraphApplication: Graph Boot Entry & Lifecycle"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, Bean, Environment, String, RoutingGraphApplication

### Community 9 - "RoutingApplication: Simple Boot Entry & Lifecycle"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, Bean, Environment, String, RoutingApplication

### Community 10 - "RoutingGraphService: CompiledGraph Invocation & Results"
Cohesion: 0.33
Nodes (4): CompiledGraph, String, RoutingGraphService, RoutingGraphResult

### Community 11 - "Graph GitHubStubTools: search_code/issue/pr Tools"
Cohesion: 0.52
Nodes (3): String, Tool, GitHubStubTools

### Community 12 - "Simple GitHubStubTools: search_code/issue/pr Tools"
Cohesion: 0.52
Nodes (3): String, Tool, GitHubStubTools

### Community 13 - "Graph NotionStubTools: search_notion/get_page Tools"
Cohesion: 0.53
Nodes (3): String, Tool, NotionStubTools

### Community 14 - "Graph SlackStubTools: search_slack/get_thread Tools"
Cohesion: 0.53
Nodes (3): String, Tool, SlackStubTools

### Community 15 - "Simple NotionStubTools: search_notion/get_page Tools"
Cohesion: 0.53
Nodes (3): String, Tool, NotionStubTools

### Community 16 - "Simple SlackStubTools: search_slack/get_thread Tools"
Cohesion: 0.53
Nodes (3): String, Tool, SlackStubTools

## Knowledge Gaps
- **24 isolated node(s):** `String`, `RoutingGraphService`, `String`, `RoutingGraphResult`, `RoutingGraphService` (+19 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `AgentStaticLoader` connect `Simple AgentStaticLoader: LlmRoutingAgent Discovery & Loading` to `Graph AgentStaticLoader: LlmRoutingAgent Discovery & Loading`?**
  _High betweenness centrality (0.004) - this node is a cross-community bridge._
- **What connects `String`, `RoutingGraphService`, `String` to the rest of the system?**
  _24 weakly-connected nodes found - possible documentation gaps or missing edges._