# Graph Report - /workspace/examples/deepresearch  (2026-05-28)

## Corpus Check
- Corpus is ~2,053 words - fits in a single context window. You may not need a graph.

## Summary
- 79 nodes · 134 edges · 6 communities
- Extraction: 95% EXTRACTED · 5% INFERRED · 0% AMBIGUOUS · INFERRED: 7 edges (avg confidence: 0.81)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_README Agent Architecture & Core Concepts|README: Agent Architecture & Core Concepts]]
- [[_COMMUNITY_DeepResearchAgent Main Agent Configuration|DeepResearchAgent: Main Agent Configuration]]
- [[_COMMUNITY_README Context, Filesystem & Critique Sub-agent|README: Context, Filesystem & Critique Sub-agent]]
- [[_COMMUNITY_AgentStaticLoader Agent Registry & Discovery|AgentStaticLoader: Agent Registry & Discovery]]
- [[_COMMUNITY_DeepResearch Application Bootstrap & Listener|DeepResearch Application Bootstrap & Listener]]
- [[_COMMUNITY_README MCP Integration, ChatUI & YML Config|README: MCP Integration, ChatUI & YML Config]]

## God Nodes (most connected - your core abstractions)
1. `DeepResearch Agent` - 18 edges
2. `Spring AI Alibaba Framework` - 8 edges
3. `Interceptor Middleware` - 8 edges
4. `Spring AI MCP Client` - 7 edges
5. `Spring Application Configuration (application.yml)` - 7 edges
6. `DeepResearchAgent` - 6 edges
7. `AgentStaticLoader` - 5 edges
8. `ToolCallback` - 5 edges
9. `File System & Context Management` - 5 edges
10. `ReactAgent (ReAct Pattern)` - 5 edges

## Surprising Connections (you probably didn't know these)
- `Spring Application Configuration (application.yml)` --conceptually_related_to--> `DeepResearch Agent`  [EXTRACTED]
  examples/deepresearch/src/main/resources/application.yml → examples/deepresearch/README.md
- `MCP Client Enabled Flag` --conceptually_related_to--> `Spring AI MCP Client`  [EXTRACTED]
  examples/deepresearch/src/main/resources/application.yml → examples/deepresearch/README.md
- `MCP Request Timeout 60000ms` --conceptually_related_to--> `Spring AI MCP Client`  [EXTRACTED]
  examples/deepresearch/src/main/resources/application.yml → examples/deepresearch/README.md
- `MCP Tool Callback Enabled` --conceptually_related_to--> `Spring AI MCP Client`  [EXTRACTED]
  examples/deepresearch/src/main/resources/application.yml → examples/deepresearch/README.md
- `DashScope API Key Config (${AI_DASHSCOPE_API_KEY})` --conceptually_related_to--> `Alibaba Cloud Bailian`  [INFERRED]
  examples/deepresearch/src/main/resources/application.yml → examples/deepresearch/README.md

## Communities (6 total, 0 thin omitted)

### Community 0 - "README: Agent Architecture & Core Concepts"
Cohesion: 0.16
Nodes (19): Agent Studio UI, Agentic Architecture (Beyond Simple Tool-Calling), Alibaba Cloud Bailian, Application.java Entry Point, Conversation History Persistence, DashScope Chat Model, DeepResearch Agent, Event Hooks (+11 more)

### Community 1 - "DeepResearchAgent: Main Agent Configuration"
Cohesion: 0.30
Nodes (8): DeepResearchAgent, Prompts, List, String, Interceptor, ReactAgent, SubAgentSpec, ToolCallback

### Community 2 - "README: Context, Filesystem & Critique Sub-agent"
Cohesion: 0.22
Nodes (13): Context Window Overflow Prevention, ContextEditingInterceptor, critique-agent Subagent, File System & Context Management, File System Tools (ls/read_file/write_file/edit_file/glob/grep), FilesystemInterceptor, Interceptor Middleware, LargeResultEvictionInterceptor (+5 more)

### Community 3 - "AgentStaticLoader: Agent Registry & Discovery"
Cohesion: 0.27
Nodes (8): Agent, AgentLoader, List, String, AgentStaticLoader, Nonnull, Override, ToolCallbackProvider

### Community 4 - "DeepResearch Application Bootstrap & Listener"
Cohesion: 0.29
Nodes (7): String, ApplicationListener, ApplicationReadyEvent, Bean, Application, Environment, McpSyncHttpClientRequestCustomizer

### Community 5 - "README: MCP Integration, ChatUI & YML Config"
Cohesion: 0.29
Nodes (10): Chat UI (localhost:8080/chatui/index.html), Jina AI Search Service, Spring AI MCP Client, MCP Tool Integration, Spring Application Configuration (application.yml), Jina MCP SSE Connection (https://mcp.jina.ai/sse), MCP Client Enabled Flag, MCP Request Timeout 60000ms (+2 more)

## Knowledge Gaps
- **5 isolated node(s):** `String`, `Prompts`, `JDK 17+`, `Maven Build System`, `Application.java Entry Point`
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `DeepResearch Agent` connect `README: Agent Architecture & Core Concepts` to `README: Context, Filesystem & Critique Sub-agent`, `README: MCP Integration, ChatUI & YML Config`?**
  _High betweenness centrality (0.187) - this node is a cross-community bridge._
- **Why does `Interceptor Middleware` connect `README: Context, Filesystem & Critique Sub-agent` to `README: Agent Architecture & Core Concepts`?**
  _High betweenness centrality (0.048) - this node is a cross-community bridge._
- **Why does `Spring Application Configuration (application.yml)` connect `README: MCP Integration, ChatUI & YML Config` to `README: Agent Architecture & Core Concepts`?**
  _High betweenness centrality (0.034) - this node is a cross-community bridge._
- **What connects `String`, `Prompts`, `JDK 17+` to the rest of the system?**
  _5 weakly-connected nodes found - possible documentation gaps or missing edges._