# Graph Report - /workspace/spring-boot-starters/spring-ai-alibaba-starter-agentscope  (2026-05-26)

## Corpus Check
- Corpus is ~8,982 words - fits in a single context window. You may not need a graph.

## Summary
- 215 nodes · 488 edges · 12 communities (10 shown, 2 thin omitted)
- Extraction: 82% EXTRACTED · 18% INFERRED · 0% AMBIGUOUS · INFERRED: 90 edges (avg confidence: 0.8)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Agent Core Builder State|Agent Core Builder State]]
- [[_COMMUNITY_Agent Integration Tests|Agent Integration Tests]]
- [[_COMMUNITY_Message Conversion Utils|Message Conversion Utils]]
- [[_COMMUNITY_Routing Agent Builder Flow|Routing Agent Builder Flow]]
- [[_COMMUNITY_Routing Node Decision Logic|Routing Node Decision Logic]]
- [[_COMMUNITY_Routing Merge Synthesis|Routing Merge Synthesis]]
- [[_COMMUNITY_Class Definitions|Class Definitions]]
- [[_COMMUNITY_Graph Building Strategy|Graph Building Strategy]]
- [[_COMMUNITY_Tool Context State Update|Tool Context State Update]]
- [[_COMMUNITY_AutoConfig Strategy Registrar|AutoConfig Strategy Registrar]]
- [[_COMMUNITY_Routing Schema Decision|Routing Schema Decision]]
- [[_COMMUNITY_Flow Auto Configuration|Flow Auto Configuration]]

## God Nodes (most connected - your core abstractions)
1. `AgentScopeAgentBuilder` - 13 edges
2. `Test` - 12 edges
3. `DisplayName` - 12 edges
4. `Msg` - 12 edges
5. `AgentScopeMessageUtils` - 11 edges
6. `AgentScopeAgent` - 10 edges
7. `String` - 10 edges
8. `AgentScopeRoutingAgent` - 10 edges
9. `AgentScopeRoutingNode` - 9 edges
10. `AgentScopeRoutingGraphBuildingStrategy` - 9 edges

## Surprising Connections (you probably didn't know these)
- `AgentScopeAgent` --semantically_similar_to--> `AgentScopeRoutingAgent`  [INFERRED] [semantically similar]
  spring-boot-starters/spring-ai-alibaba-starter-agentscope/src/main/java/com/alibaba/cloud/ai/agent/agentscope/AgentScopeAgent.java → spring-boot-starters/spring-ai-alibaba-starter-agentscope/src/main/java/com/alibaba/cloud/ai/agent/agentscope/flow/AgentScopeRoutingAgent.java
- `AgentScopeRoutingMergeNode` --conceptually_related_to--> `AgentScopeRoutingNode`  [INFERRED]
  spring-boot-starters/spring-ai-alibaba-starter-agentscope/src/main/java/com/alibaba/cloud/ai/agent/agentscope/flow/AgentScopeRoutingMergeNode.java → spring-boot-starters/spring-ai-alibaba-starter-agentscope/src/main/java/com/alibaba/cloud/ai/agent/agentscope/flow/AgentScopeRoutingNode.java
- `AgentScopeRoutingAgent` --conceptually_related_to--> `AgentScopeRoutingStrategyRegistrar`  [INFERRED]
  spring-boot-starters/spring-ai-alibaba-starter-agentscope/src/main/java/com/alibaba/cloud/ai/agent/agentscope/flow/AgentScopeRoutingAgent.java → spring-boot-starters/spring-ai-alibaba-starter-agentscope/src/main/java/com/alibaba/cloud/ai/agent/agentscope/flow/AgentScopeFlowAutoConfiguration.java
- `AgentScopeAgent` --inherits--> `BaseAgent`  [EXTRACTED]
  main/java/com/alibaba/cloud/ai/agent/agentscope/AgentScopeAgent.java → main/java/com/alibaba/cloud/ai/agent/agentscope/flow/AgentScopeRoutingMergeNode.java
- `AgentScopeMessageUtils` --conceptually_related_to--> `ReActAgentNodeAction (inner class of AgentScopeAgent)`  [INFERRED]
  spring-boot-starters/spring-ai-alibaba-starter-agentscope/src/main/java/com/alibaba/cloud/ai/agent/agentscope/AgentScopeMessageUtils.java → spring-boot-starters/spring-ai-alibaba-starter-agentscope/src/main/java/com/alibaba/cloud/ai/agent/agentscope/AgentScopeAgent.java

## Hyperedges (group relationships)
- **AgentScope Routing Flow: Graph Building Pipeline** — AgentScopeRoutingAgent_AgentScopeRoutingAgent, AgentScopeRoutingGraphBuildingStrategy_AgentScopeRoutingGraphBuildingStrategy, AgentScopeRoutingNode_AgentScopeRoutingNode, AgentScopeRoutingMergeNode_AgentScopeRoutingMergeNode, AgentScopeFlowAutoConfiguration_AgentScopeRoutingStrategyRegistrar [EXTRACTED 0.90]
- **Message Conversion Utility: Spring AI ↔ AgentScope** — AgentScopeMessageUtils_AgentScopeMessageUtils, AgentScopeAgent_ReActAgentNodeAction, AgentScopeRoutingNode_AgentScopeRoutingNode [EXTRACTED 1.00]
- **Builder Pattern: AgentScopeAgent Construction** — AgentScopeAgent_AgentScopeAgent, AgentScopeAgent_AgentScopeAgentBuilder, AgentScopeAgent_ReActAgentNodeAction [EXTRACTED 1.00]
- **Routing Decision Schema: Structured Output Pipeline** — RoutingDecisionSchema_RoutingDecisionSchema, RoutingDecisionSchema_AgentRoutingSchema, AgentScopeRoutingNode_AgentScopeRoutingNode [EXTRACTED 1.00]
- **ToolContext Integration: Graph State ↔ AgentScope Tool** — UpdateExtraStateTool_UpdateExtraStateTool, AgentScopeAgent_ReActAgentNodeAction, AgentScopeAgentTest_AgentScopeAgentTest [INFERRED 0.80]

## Communities (12 total, 2 thin omitted)

### Community 0 - "Agent Core Builder State"
Cohesion: 0.10
Nodes (22): AgentScopeAgent, AgentScopeAgentBuilder, ReActAgentNodeAction, AgentScopeAgentBuilder, Builder, KeyStrategy, AssistantMessage, KeyStrategyFactory (+14 more)

### Community 1 - "Agent Integration Tests"
Cohesion: 0.17
Nodes (13): AgentScopeAgentTest, AsNodeTests, GraphAgentScopeToolContextTests, SequentialIntegrationTests, StandaloneTests, BeforeAll, DisplayName, EnabledIfEnvironmentVariable (+5 more)

### Community 2 - "Message Conversion Utils"
Cohesion: 0.18
Nodes (13): AgentScopeMessageUtils, ContentBlock, Event, EventType, AssistantMessage, List, Map, Message (+5 more)

### Community 3 - "Routing Agent Builder Flow"
Cohesion: 0.14
Nodes (9): AgentScopeRoutingAgentBuilder, AgentScopeRoutingAgent, AgentScopeRoutingAgentBuilder, FlowAgent, FlowGraphConfig, Model, Override, StateGraph (+1 more)

### Community 4 - "Routing Node Decision Logic"
Cohesion: 0.19
Nodes (13): Agent, AgentScopeRoutingNode, List, Message, Model, OverAllState, Override, RunnableConfig (+5 more)

### Community 5 - "Routing Merge Synthesis"
Cohesion: 0.26
Nodes (9): AgentScopeRoutingMergeNode, List, Map, Model, Object, OverAllState, Override, String (+1 more)

### Community 6 - "Class Definitions"
Cohesion: 0.19
Nodes (15): AgentScopeAgentTest, AgentScopeAgent, AgentScopeAgentBuilder, ReActAgentNodeAction (inner class of AgentScopeAgent), AgentScopeRoutingStrategyRegistrar, AgentScopeMessageUtils, AgentScopeRoutingAgentTest, AgentScopeRoutingAgent (+7 more)

### Community 7 - "Graph Building Strategy"
Cohesion: 0.25
Nodes (7): AbstractFlowGraphBuildingStrategy, AgentScopeRoutingGraphBuildingStrategy, FlowGraphConfig, KeyStrategyFactory, Override, String, BaseAgent

### Community 8 - "Tool Context State Update"
Cohesion: 0.43
Nodes (5): UpdateExtraStateTool, OverAllState, String, Tool, ToolContext

### Community 9 - "AutoConfig Strategy Registrar"
Cohesion: 0.33
Nodes (4): AgentScopeRoutingStrategyRegistrar, Bean, AgentScopeFlowAutoConfiguration, AgentScopeRoutingStrategyRegistrar

## Knowledge Gaps
- **15 isolated node(s):** `Object`, `SuppressWarnings`, `SuppressWarnings`, `Model`, `Override` (+10 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `AgentScopeAgentBuilder` connect `Agent Core Builder State` to `Agent Integration Tests`?**
  _High betweenness centrality (0.095) - this node is a cross-community bridge._
- **Why does `Msg` connect `Message Conversion Utils` to `Agent Core Builder State`, `Agent Integration Tests`, `Routing Node Decision Logic`, `Routing Merge Synthesis`?**
  _High betweenness centrality (0.058) - this node is a cross-community bridge._
- **What connects `Object`, `SuppressWarnings`, `SuppressWarnings` to the rest of the system?**
  _15 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Agent Core Builder State` be split into smaller, more focused modules?**
  _Cohesion score 0.0975609756097561 - nodes in this community are weakly interconnected._
- **Should `Routing Agent Builder Flow` be split into smaller, more focused modules?**
  _Cohesion score 0.13768115942028986 - nodes in this community are weakly interconnected._