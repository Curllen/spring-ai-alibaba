# Graph Report - /workspace/examples/multiagent-patterns/supervisor  (2026-05-29)

## Corpus Check
- Corpus is ~2,435 words - fits in a single context window. You may not need a graph.

## Summary
- 84 nodes · 138 edges · 9 communities
- Extraction: 79% EXTRACTED · 21% INFERRED · 0% AMBIGUOUS · INFERRED: 29 edges (avg confidence: 0.87)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Supervisor Pattern Agent Design & Tool Orchestration|Supervisor Pattern: Agent Design & Tool Orchestration]]
- [[_COMMUNITY_SupervisorConfig Bean Wiring & AgentTool Assembly|SupervisorConfig: Bean Wiring & AgentTool Assembly]]
- [[_COMMUNITY_AgentStaticLoader Studio Agent Registry|AgentStaticLoader: Studio Agent Registry]]
- [[_COMMUNITY_SupervisorApplication Spring Boot Entry & Lifecycle|SupervisorApplication: Spring Boot Entry & Lifecycle]]
- [[_COMMUNITY_SupervisorRunner Demo Scenarios Execution|SupervisorRunner: Demo Scenarios Execution]]
- [[_COMMUNITY_CalendarStubTools Stub Calendar API Methods|CalendarStubTools: Stub Calendar API Methods]]
- [[_COMMUNITY_EmailStubTools Stub Email API Method|EmailStubTools: Stub Email API Method]]
- [[_COMMUNITY_DashScope API & Application Configuration|DashScope API & Application Configuration]]
- [[_COMMUNITY_Demo Runner Toggle & SupervisorRunner Config|Demo Runner Toggle & SupervisorRunner Config]]

## God Nodes (most connected - your core abstractions)
1. `Supervisor Agent` - 9 edges
2. `Calendar Agent` - 9 edges
3. `Email Agent` - 9 edges
4. `SupervisorConfig` - 7 edges
5. `Bean` - 7 edges
6. `AgentStaticLoader` - 5 edges
7. `schedule_event Tool` - 5 edges
8. `manage_email Tool` - 5 edges
9. `Agent Isolation` - 5 edges
10. `SupervisorRunner` - 4 edges

## Surprising Connections (you probably didn't know these)
- `SupervisorApplication` --entry_point_for--> `supervisor-personal-assistant Application`  [EXTRACTED]
  examples/multiagent-patterns/supervisor/README.md → examples/multiagent-patterns/supervisor/src/main/resources/application.yml
- `spring.ai.dashscope.api-key Config` --configures--> `DashScope API Key`  [EXTRACTED]
  examples/multiagent-patterns/supervisor/src/main/resources/application.yml → examples/multiagent-patterns/supervisor/README.md
- `supervisor.run-examples Config` --implements--> `supervisor.run-examples`  [EXTRACTED]
  examples/multiagent-patterns/supervisor/src/main/resources/application.yml → examples/multiagent-patterns/supervisor/README.md

## Hyperedges (group relationships)
- **Supervisor Multi-Agent Orchestration** — readme_supervisor_agent, readme_calendar_agent, readme_email_agent, readme_agent_tool [EXTRACTED 1.00]
- **Tool Wrapping per Agent Pattern** — readme_schedule_event_tool, readme_calendar_agent, readme_agent_tool, readme_string_input_type_design [EXTRACTED 1.00]
- **Demo Multi-Domain Agent Flow** — readme_demo_scenarios, readme_supervisor_agent, readme_schedule_event_tool, readme_manage_email_tool [EXTRACTED 1.00]

## Communities (9 total, 0 thin omitted)

### Community 0 - "Supervisor Pattern: Agent Design & Tool Orchestration"
Cohesion: 0.20
Nodes (21): Agent Isolation, AgentTool, AssistantMessage, Calendar Agent, CalendarStubTools, Demo Scenarios, Email Agent, EmailStubTools (+13 more)

### Community 1 - "SupervisorConfig: Bean Wiring & AgentTool Assembly"
Cohesion: 0.34
Nodes (7): CalendarStubTools, ChatModel, EmailStubTools, MemorySaver, SupervisorConfig, Bean, ReactAgent

### Community 2 - "AgentStaticLoader: Studio Agent Registry"
Cohesion: 0.27
Nodes (8): Agent, AgentLoader, List, Override, ReactAgent, String, Nonnull, AgentStaticLoader

### Community 3 - "SupervisorApplication: Spring Boot Entry & Lifecycle"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, Environment, SupervisorApplication, Bean, String

### Community 4 - "SupervisorRunner: Demo Scenarios Execution"
Cohesion: 0.36
Nodes (5): ApplicationArguments, ApplicationRunner, SupervisorRunner, Override, ReactAgent

### Community 5 - "CalendarStubTools: Stub Calendar API Methods"
Cohesion: 0.52
Nodes (4): CalendarStubTools, List, String, Tool

### Community 6 - "EmailStubTools: Stub Email API Method"
Cohesion: 0.47
Nodes (4): EmailStubTools, List, String, Tool

### Community 7 - "DashScope API & Application Configuration"
Cohesion: 0.50
Nodes (4): spring.ai.dashscope.api-key Config, supervisor-personal-assistant Application, DashScope API Key, SupervisorApplication

### Community 8 - "Demo Runner Toggle & SupervisorRunner Config"
Cohesion: 0.67
Nodes (3): supervisor.run-examples Config, supervisor.run-examples, SupervisorRunner

## Knowledge Gaps
- **8 isolated node(s):** `String`, `Override`, `String`, `SupervisorApplication`, `Demo Scenarios` (+3 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Supervisor Agent` connect `Supervisor Pattern: Agent Design & Tool Orchestration` to `Demo Runner Toggle & SupervisorRunner Config`?**
  _High betweenness centrality (0.046) - this node is a cross-community bridge._
- **Why does `Spring AI Alibaba` connect `Supervisor Pattern: Agent Design & Tool Orchestration` to `DashScope API & Application Configuration`?**
  _High betweenness centrality (0.027) - this node is a cross-community bridge._
- **Are the 5 inferred relationships involving `Calendar Agent` (e.g. with `Agent Isolation` and `Email Agent`) actually correct?**
  _`Calendar Agent` has 5 INFERRED edges - model-reasoned connections that need verification._
- **Are the 5 inferred relationships involving `Email Agent` (e.g. with `Agent Isolation` and `Calendar Agent`) actually correct?**
  _`Email Agent` has 5 INFERRED edges - model-reasoned connections that need verification._
- **What connects `String`, `Override`, `String` to the rest of the system?**
  _8 weakly-connected nodes found - possible documentation gaps or missing edges._