# Graph Report - /workspace/examples/multiagent-patterns/subagent  (2026-05-29)

## Corpus Check
- Corpus is ~2,583 words - fits in a single context window. You may not need a graph.

## Summary
- 69 nodes · 119 edges · 6 communities
- Extraction: 87% EXTRACTED · 13% INFERRED · 0% AMBIGUOUS · INFERRED: 16 edges (avg confidence: 0.87)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Sub-Agent Definitions & Tool Specifications|Sub-Agent Definitions & Tool Specifications]]
- [[_COMMUNITY_Agent Configuration, TaskToolsBuilder & Task Delegation|Agent Configuration, TaskToolsBuilder & Task Delegation]]
- [[_COMMUNITY_AgentStaticLoader & SubagentTools Data Holder|AgentStaticLoader & SubagentTools Data Holder]]
- [[_COMMUNITY_SubagentConfig Bean Wiring & Orchestrator Assembly|SubagentConfig: Bean Wiring & Orchestrator Assembly]]
- [[_COMMUNITY_SubagentApplication Spring Boot Entry & Lifecycle|SubagentApplication: Spring Boot Entry & Lifecycle]]
- [[_COMMUNITY_SubagentRunner Interactive Chat & Agent Invocation|SubagentRunner: Interactive Chat & Agent Invocation]]

## God Nodes (most connected - your core abstractions)
1. `Tech Due Diligence Assistant (Orchestrator)` - 12 edges
2. `General Purpose Sub-Agent` - 7 edges
3. `glob_search Tool` - 7 edges
4. `grep_search Tool` - 7 edges
5. `SubagentConfig` - 5 edges
6. `Bean` - 5 edges
7. `AgentStaticLoader` - 5 edges
8. `Subagent (TaskTool) Pattern` - 5 edges
9. `Codebase Explorer Sub-Agent` - 5 edges
10. `Markdown-based Agent Definition` - 5 edges

## Surprising Connections (you probably didn't know these)
- `Codebase Explorer Sub-Agent` --semantically_similar_to--> `codebase-explorer Agent Specification`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/subagent/README.md → examples/multiagent-patterns/subagent/src/main/resources/agents/codebase-explorer.md
- `Web Researcher Sub-Agent` --semantically_similar_to--> `web-researcher Agent Specification`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/subagent/README.md → examples/multiagent-patterns/subagent/src/main/resources/agents/web-researcher.md
- `General Purpose Sub-Agent` --semantically_similar_to--> `general-purpose Agent Specification`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/subagent/README.md → examples/multiagent-patterns/subagent/src/main/resources/agents/general-purpose.md
- `Markdown-based Agent Definition` --implements--> `codebase-explorer Agent Specification`  [INFERRED]
  examples/multiagent-patterns/subagent/README.md → examples/multiagent-patterns/subagent/src/main/resources/agents/codebase-explorer.md
- `Markdown-based Agent Definition` --implements--> `general-purpose Agent Specification`  [INFERRED]
  examples/multiagent-patterns/subagent/README.md → examples/multiagent-patterns/subagent/src/main/resources/agents/general-purpose.md

## Hyperedges (group relationships)
- **Orchestrator Planning → Delegation → Specialized Sub-Agents** — readme_tech_due_diligence_assistant, readme_write_todos, readme_task_tools, readme_codebase_explorer_ref, readme_web_researcher_ref, readme_general_purpose_ref, readme_dependency_analyzer_ref [INFERRED 0.80]
- **TaskToolsBuilder Bridges Markdown and API Agent Definitions** — readme_tasktoolsbuilder, readme_markdown_agent_definition, readme_api_agent_definition [EXTRACTED 1.00]

## Communities (6 total, 0 thin omitted)

### Community 0 - "Sub-Agent Definitions & Tool Specifications"
Cohesion: 0.33
Nodes (14): subagent.workspace-path Config, codebase-explorer Agent Specification, general-purpose Agent Specification, Codebase Explorer Sub-Agent, Dependency Analyzer Sub-Agent, General Purpose Sub-Agent, glob_search Tool, grep_search Tool (+6 more)

### Community 1 - "Agent Configuration, TaskToolsBuilder & Task Delegation"
Cohesion: 0.18
Nodes (13): DashScope AI API Configuration, subagent.run-interactive Config, subagent-tech-due-diligence Application, API-based (Programmatic) Agent Definition, ChatModel, Markdown-based Agent Definition, ReactAgent, subagent-demo (Spring AI Community) (+5 more)

### Community 2 - "AgentStaticLoader & SubagentTools Data Holder"
Cohesion: 0.24
Nodes (8): Agent, AgentLoader, Override, ReactAgent, String, List, Nonnull, AgentStaticLoader

### Community 3 - "SubagentConfig: Bean Wiring & Orchestrator Assembly"
Cohesion: 0.35
Nodes (7): ChatModel, SubagentConfig, Bean, ReactAgent, String, SubagentTools, TodoListInterceptor

### Community 4 - "SubagentApplication: Spring Boot Entry & Lifecycle"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, Environment, SubagentApplication, Bean, String

### Community 5 - "SubagentRunner: Interactive Chat & Agent Invocation"
Cohesion: 0.36
Nodes (5): ApplicationArguments, ApplicationRunner, SubagentRunner, Override, ReactAgent

## Knowledge Gaps
- **8 isolated node(s):** `String`, `Override`, `String`, `TodoListInterceptor`, `ToolCallback` (+3 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Tech Due Diligence Assistant (Orchestrator)` connect `Sub-Agent Definitions & Tool Specifications` to `Agent Configuration, TaskToolsBuilder & Task Delegation`?**
  _High betweenness centrality (0.072) - this node is a cross-community bridge._
- **Why does `List` connect `AgentStaticLoader & SubagentTools Data Holder` to `SubagentConfig: Bean Wiring & Orchestrator Assembly`?**
  _High betweenness centrality (0.069) - this node is a cross-community bridge._
- **Are the 5 inferred relationships involving `Tech Due Diligence Assistant (Orchestrator)` (e.g. with `ChatModel` and `Codebase Explorer Sub-Agent`) actually correct?**
  _`Tech Due Diligence Assistant (Orchestrator)` has 5 INFERRED edges - model-reasoned connections that need verification._
- **Are the 4 inferred relationships involving `General Purpose Sub-Agent` (e.g. with `Codebase Explorer Sub-Agent` and `general-purpose Agent Specification`) actually correct?**
  _`General Purpose Sub-Agent` has 4 INFERRED edges - model-reasoned connections that need verification._
- **What connects `String`, `Override`, `String` to the rest of the system?**
  _8 weakly-connected nodes found - possible documentation gaps or missing edges._