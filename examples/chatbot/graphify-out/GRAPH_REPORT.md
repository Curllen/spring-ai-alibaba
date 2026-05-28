# Graph Report - /workspace/examples/chatbot  (2026-05-28)

## Corpus Check
- Corpus is ~1,579 words - fits in a single context window. You may not need a graph.

## Summary
- 56 nodes · 83 edges · 5 communities
- Extraction: 98% EXTRACTED · 2% INFERRED · 0% AMBIGUOUS · INFERRED: 2 edges (avg confidence: 0.82)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_ChatbotAgent ReAct Agent Configuration & Tools|ChatbotAgent: ReAct Agent Configuration & Tools]]
- [[_COMMUNITY_PythonTool Code Execution & Engine Integration|PythonTool: Code Execution & Engine Integration]]
- [[_COMMUNITY_README Documentation & Setup Guide|README Documentation & Setup Guide]]
- [[_COMMUNITY_AgentStaticLoader Agent Registry & Discovery|AgentStaticLoader: Agent Registry & Discovery]]
- [[_COMMUNITY_ChatbotApplication Spring Boot Bootstrap|ChatbotApplication: Spring Boot Bootstrap]]

## God Nodes (most connected - your core abstractions)
1. `ReAct Agent Example` - 8 edges
2. `ChatbotAgent` - 6 edges
3. `Bean` - 6 edges
4. `AgentStaticLoader` - 5 edges
5. `ToolCallback` - 5 edges
6. `ChatBot Application` - 5 edges
7. `PythonTool` - 4 edges
8. `String` - 3 edges
9. `ChatbotApplication` - 3 edges
10. `Agent` - 3 edges

## Surprising Connections (you probably didn't know these)
- None detected - all connections are within the same source files.

## Communities (5 total, 0 thin omitted)

### Community 0 - "ChatbotAgent: ReAct Agent Configuration & Tools"
Cohesion: 0.36
Nodes (6): ChatbotAgent, Bean, ToolCallback, ChatModel, MemorySaver, ReactAgent

### Community 1 - "PythonTool: Code Execution & Engine Integration"
Cohesion: 0.23
Nodes (7): PythonRequest, PythonTool, PythonRequest, Override, String, ToolCallback, ToolContext

### Community 2 - "README Documentation & Setup Guide"
Cohesion: 0.23
Nodes (12): AI_DASHSCOPE_API_KEY, ChatBot Application, Chat UI, DashScope LLM Provider, spring-ai-alibaba GitHub Repository, JDK 17+, Maven Wrapper (mvnw), ReactAgent (+4 more)

### Community 3 - "AgentStaticLoader: Agent Registry & Discovery"
Cohesion: 0.31
Nodes (7): Agent, AgentLoader, Override, String, AgentStaticLoader, List, Nonnull

### Community 4 - "ChatbotApplication: Spring Boot Bootstrap"
Cohesion: 0.33
Nodes (6): ApplicationListener, ApplicationReadyEvent, ChatbotApplication, Bean, String, Environment

## Knowledge Gaps
- **7 isolated node(s):** `PythonRequest`, `Override`, `String`, `JDK 17+`, `AI_DASHSCOPE_API_KEY` (+2 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **What connects `PythonRequest`, `Override`, `String` to the rest of the system?**
  _7 weakly-connected nodes found - possible documentation gaps or missing edges._