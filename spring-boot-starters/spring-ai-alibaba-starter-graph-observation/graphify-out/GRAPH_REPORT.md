# Graph Report - /workspace/spring-boot-starters/spring-ai-alibaba-starter-graph-observation  (2026-05-27)

## Corpus Check
- Corpus is ~2,025 words - fits in a single context window. You may not need a graph.

## Summary
- 64 nodes · 114 edges · 8 communities (4 shown, 4 thin omitted)
- Extraction: 99% EXTRACTED · 1% INFERRED · 0% AMBIGUOUS · INFERRED: 1 edges (avg confidence: 0.8)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Observation Auto-Config Integration Tests|Observation Auto-Config Integration Tests]]
- [[_COMMUNITY_Graph Observation Handlers Config|Graph Observation Handlers Config]]
- [[_COMMUNITY_Chat Model Observation Convention|Chat Model Observation Convention]]
- [[_COMMUNITY_Observation Test Configuration Beans|Observation Test Configuration Beans]]
- [[_COMMUNITY_Observation Auto-Configuration Core|Observation Auto-Configuration Core]]
- [[_COMMUNITY_Observation Config Properties|Observation Config Properties]]
- [[_COMMUNITY_Chat Model Convention Bean|Chat Model Convention Bean]]
- [[_COMMUNITY_Spring Config Metadata Resources|Spring Config Metadata Resources]]

## God Nodes (most connected - your core abstractions)
1. `GraphObservationAutoConfigurationTest` - 13 edges
2. `Test` - 12 edges
3. `Bean` - 8 edges
4. `ConditionalOnMissingBean` - 8 edges
5. `GraphObservationAutoConfiguration` - 5 edges
6. `ObjectProvider` - 4 edges
7. `ObservationRegistry` - 4 edges
8. `GraphObservationLifecycleListener` - 4 edges
9. `ObservationHandlersConfiguration` - 4 edges
10. `MeterRegistry` - 4 edges

## Surprising Connections (you probably didn't know these)
- None detected - all connections are within the same source files.

## Communities (8 total, 4 thin omitted)

### Community 1 - "Graph Observation Handlers Config"
Cohesion: 0.35
Nodes (7): ObservationHandlersConfiguration, ObservationThreadLocalAccessorRegistrar, GraphEdgeObservationHandler, GraphNodeObservationHandler, GraphObservationHandler, Bean, MeterRegistry

### Community 2 - "Chat Model Observation Convention"
Cohesion: 0.31
Nodes (7): ChatModelObservationContext, DefaultChatModelObservationConvention, KeyValues, Message, SpringAiAlibabaChatModelObservationConvention, Override, String

### Community 3 - "Observation Test Configuration Beans"
Cohesion: 0.31
Nodes (6): BeforeEach, TestConfiguration, TestConfigurationWithMeterRegistry, Bean, MeterRegistry, ObservationRegistry

### Community 4 - "Observation Auto-Configuration Core"
Cohesion: 0.31
Nodes (7): CompileConfig, ConditionalOnClass, GraphObservationAutoConfiguration, GraphObservationLifecycleListener, ObservationRegistry, ObjectProvider, ObservationThreadLocalAccessorRegistrar

## Knowledge Gaps
- **7 isolated node(s):** `groups`, `properties`, `ObservationThreadLocalAccessorRegistrar`, `ChatModelObservationConvention`, `ObservationThreadLocalAccessorRegistrar` (+2 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **4 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `GraphObservationLifecycleListener` connect `Observation Auto-Configuration Core` to `Graph Observation Handlers Config`, `Observation Test Configuration Beans`?**
  _High betweenness centrality (0.175) - this node is a cross-community bridge._
- **Why does `GraphObservationAutoConfigurationTest` connect `Observation Auto-Config Integration Tests` to `Observation Test Configuration Beans`?**
  _High betweenness centrality (0.169) - this node is a cross-community bridge._
- **Why does `Test` connect `Observation Auto-Config Integration Tests` to `Observation Test Configuration Beans`?**
  _High betweenness centrality (0.150) - this node is a cross-community bridge._
- **What connects `groups`, `properties`, `ObservationThreadLocalAccessorRegistrar` to the rest of the system?**
  _7 weakly-connected nodes found - possible documentation gaps or missing edges._