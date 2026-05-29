# Graph Report - /workspace/examples/multiagent-patterns/pipeline  (2026-05-29)

## Corpus Check
- Corpus is ~1,958 words - fits in a single context window. You may not need a graph.

## Summary
- 52 nodes · 72 edges · 8 communities (7 shown, 1 thin omitted)
- Extraction: 94% EXTRACTED · 6% INFERRED · 0% AMBIGUOUS · INFERRED: 4 edges (avg confidence: 0.84)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Pipeline Agents SequentialLoop SQL Patterns & Framework|Pipeline Agents: Sequential/Loop SQL Patterns & Framework]]
- [[_COMMUNITY_PipelineApplication Spring Boot Entry Point & Lifecycle|PipelineApplication: Spring Boot Entry Point & Lifecycle]]
- [[_COMMUNITY_AgentLoader Config SequentialParallelLoop Agent Beans|AgentLoader Config: Sequential/Parallel/Loop Agent Beans]]
- [[_COMMUNITY_Loop Pipeline Config LoopAgent & SQL Refinement Assembly|Loop Pipeline Config: LoopAgent & SQL Refinement Assembly]]
- [[_COMMUNITY_Parallel Pipeline Config ParallelAgent & Research Assembly|Parallel Pipeline Config: ParallelAgent & Research Assembly]]
- [[_COMMUNITY_Sequential Pipeline Config SequentialAgent & SQL Assembly|Sequential Pipeline Config: SequentialAgent & SQL Assembly]]
- [[_COMMUNITY_Parallel Research Sub-Agents TechFinanceMarket Researchers|Parallel Research Sub-Agents: Tech/Finance/Market Researchers]]
- [[_COMMUNITY_Natural Language to SQL Scenario|Natural Language to SQL Scenario]]

## God Nodes (most connected - your core abstractions)
1. `ParallelAgent: Three-Angle Parallel Research` - 6 edges
2. `LoopAgent: Iterative SQL Refinement` - 6 edges
3. `SequentialAgent: SQL Generator -> SQL Rater Pipeline` - 5 edges
4. `Spring AI Alibaba Agent Framework` - 5 edges
5. `SQL Generator Sub-Agent` - 4 edges
6. `Pipeline Agent Pattern (Sequential/Parallel/Loop)` - 4 edges
7. `PipelineApplication` - 3 edges
8. `SQL Rater Sub-Agent` - 3 edges
9. `Tech Researcher Sub-Agent` - 3 edges
10. `Finance Researcher Sub-Agent` - 3 edges

## Surprising Connections (you probably didn't know these)
- `Spring AI Alibaba Agent Framework` --references--> `DashScope API (AI Provider)`  [EXTRACTED]
  examples/multiagent-patterns/pipeline/README.md → examples/multiagent-patterns/pipeline/src/main/resources/application.yml
- `Multi-Agent Pipeline Application` --references--> `Pipeline Agent Pattern (Sequential/Parallel/Loop)`  [EXTRACTED]
  examples/multiagent-patterns/pipeline/src/main/resources/application.yml → examples/multiagent-patterns/pipeline/README.md

## Hyperedges (group relationships)
- **Pipeline Agent Pattern Triad (Sequential, Parallel, Loop)** — N1, N2, N3 [EXTRACTED 1.00]
- **SQL Generation-Rating-Optimization Closed Loop** — N5, N6, N12 [EXTRACTED 1.00]
- **Three-Angle Parallel Research (Tech/Finance/Market)** — N8, N9, N10 [EXTRACTED 1.00]

## Communities (8 total, 1 thin omitted)

### Community 0 - "Pipeline Agents: Sequential/Loop SQL Patterns & Framework"
Cohesion: 0.27
Nodes (11): SequentialAgent: SQL Generator -> SQL Rater Pipeline, DashScope API (AI Provider), Quality Score Threshold 0.5, Spring AI Alibaba Studio ChatUI, Pipeline Agent Pattern (Sequential/Parallel/Loop), MySQL SQL Target Dialect, Multi-Agent Pipeline Application, LoopAgent: Iterative SQL Refinement (+3 more)

### Community 1 - "PipelineApplication: Spring Boot Entry Point & Lifecycle"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, Environment, PipelineApplication, Bean, String

### Community 2 - "AgentLoader Config: Sequential/Parallel/Loop Agent Beans"
Cohesion: 0.43
Nodes (6): AgentLoader, PipelineAgentLoaderConfig, Bean, LoopAgent, ParallelAgent, SequentialAgent

### Community 3 - "Loop Pipeline Config: LoopAgent & SQL Refinement Assembly"
Cohesion: 0.53
Nodes (4): Bean, ChatModel, LoopAgent, LoopPipelineConfig

### Community 4 - "Parallel Pipeline Config: ParallelAgent & Research Assembly"
Cohesion: 0.53
Nodes (4): Bean, ChatModel, ParallelAgent, ParallelPipelineConfig

### Community 5 - "Sequential Pipeline Config: SequentialAgent & SQL Assembly"
Cohesion: 0.53
Nodes (4): Bean, ChatModel, SequentialAgent, SequentialPipelineConfig

### Community 6 - "Parallel Research Sub-Agents: Tech/Finance/Market Researchers"
Cohesion: 0.70
Nodes (5): Market Researcher Sub-Agent, Merged Research Report, ParallelAgent: Three-Angle Parallel Research, Tech Researcher Sub-Agent, Finance Researcher Sub-Agent

## Knowledge Gaps
- **8 isolated node(s):** `String`, `Natural Language to SQL Scenario`, `DashScope API (AI Provider)`, `Quality Score Threshold 0.5`, `Spring AI Alibaba Studio ChatUI` (+3 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `ParallelAgent: Three-Angle Parallel Research` connect `Parallel Research Sub-Agents: Tech/Finance/Market Researchers` to `Pipeline Agents: Sequential/Loop SQL Patterns & Framework`?**
  _High betweenness centrality (0.038) - this node is a cross-community bridge._
- **Why does `Spring AI Alibaba Agent Framework` connect `Pipeline Agents: Sequential/Loop SQL Patterns & Framework` to `Parallel Research Sub-Agents: Tech/Finance/Market Researchers`?**
  _High betweenness centrality (0.033) - this node is a cross-community bridge._
- **What connects `String`, `Natural Language to SQL Scenario`, `DashScope API (AI Provider)` to the rest of the system?**
  _8 weakly-connected nodes found - possible documentation gaps or missing edges._