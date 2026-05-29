# Graph Report - /workspace/examples/multiagent-patterns/workflow  (2026-05-29)

## Corpus Check
- Corpus is ~4,791 words - fits in a single context window. You may not need a graph.

## Summary
- 166 nodes · 266 edges · 13 communities
- Extraction: 96% EXTRACTED · 4% INFERRED · 0% AMBIGUOUS · INFERRED: 11 edges (avg confidence: 0.82)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Workflow Patterns RAG & SQL Agent Concepts|Workflow Patterns: RAG & SQL Agent Concepts]]
- [[_COMMUNITY_RAG Pipeline Nodes Prepare, Retrieve & VectorStore|RAG Pipeline Nodes: Prepare, Retrieve & VectorStore]]
- [[_COMMUNITY_Application Entry & Agent Runners|Application Entry & Agent Runners]]
- [[_COMMUNITY_SqlTools SQL Database Tool Methods|SqlTools: SQL Database Tool Methods]]
- [[_COMMUNITY_RagAgentConfig RAG Graph & Bean Wiring|RagAgentConfig: RAG Graph & Bean Wiring]]
- [[_COMMUNITY_SqlAgentConfig SQL Graph & Bean Wiring|SqlAgentConfig: SQL Graph & Bean Wiring]]
- [[_COMMUNITY_CallGetSchemaNode Forced Schema Tool Invocation|CallGetSchemaNode: Forced Schema Tool Invocation]]
- [[_COMMUNITY_ListTablesNode Deterministic Table Discovery|ListTablesNode: Deterministic Table Discovery]]
- [[_COMMUNITY_RewriteNode LLM Query Rewriting|RewriteNode: LLM Query Rewriting]]
- [[_COMMUNITY_RagAgentService RAG Graph Execution|RagAgentService: RAG Graph Execution]]
- [[_COMMUNITY_SqlAgentService SQL Graph Execution|SqlAgentService: SQL Graph Execution]]
- [[_COMMUNITY_WorkflowAgentLoaderConfig Studio Agent Registry|WorkflowAgentLoaderConfig: Studio Agent Registry]]
- [[_COMMUNITY_RagAgentTools News Retrieval Tool|RagAgentTools: News Retrieval Tool]]

## God Nodes (most connected - your core abstractions)
1. `SqlTools` - 11 edges
2. `List` - 11 edges
3. `RAG Agent Workflow` - 10 edges
4. `SQL Agent Workflow` - 10 edges
5. `ToolCallback` - 7 edges
6. `RagAgentConfig` - 6 edges
7. `SqlAgentConfig` - 5 edges
8. `Bean` - 5 edges
9. `Bean` - 5 edges
10. `Multi-Agent Workflow Pattern` - 5 edges

## Surprising Connections (you probably didn't know these)
- `RAG Agent Workflow` --semantically_similar_to--> `SQL Agent Workflow`  [INFERRED] [semantically similar]
  examples/multiagent-patterns/workflow/src/main/java/com/alibaba/cloud/ai/examples/multiagents/workflow/ragagent/README.md → examples/multiagent-patterns/workflow/src/main/java/com/alibaba/cloud/ai/examples/multiagents/workflow/sqlagent/README.md
- `RAG Agent Workflow` --references--> `multiagents/code/rag-agent-workflow.md (Reference Document)`  [EXTRACTED]
  examples/multiagent-patterns/workflow/src/main/java/com/alibaba/cloud/ai/examples/multiagents/workflow/ragagent/README.md → examples/multiagent-patterns/workflow/README.md
- `SQL Agent Workflow` --conceptually_related_to--> `DashScope API`  [INFERRED]
  examples/multiagent-patterns/workflow/src/main/java/com/alibaba/cloud/ai/examples/multiagents/workflow/sqlagent/README.md → examples/multiagent-patterns/workflow/src/main/resources/application.yml
- `SQL Agent Workflow` --conceptually_related_to--> `H2 In-Memory Chinook Database`  [EXTRACTED]
  examples/multiagent-patterns/workflow/src/main/java/com/alibaba/cloud/ai/examples/multiagents/workflow/sqlagent/README.md → examples/multiagent-patterns/workflow/src/main/resources/application.yml
- `EmbeddingModel (spring-ai-alibaba-starter-dashscope)` --conceptually_related_to--> `Vector Similarity Search (Deterministic)`  [INFERRED]
  examples/multiagent-patterns/workflow/README.md → examples/multiagent-patterns/workflow/src/main/java/com/alibaba/cloud/ai/examples/multiagents/workflow/ragagent/README.md

## Hyperedges (group relationships)
- **RAG Pipeline: Rewrite → Retrieve → Prepare → Agent** — query_rewrite, vector_retrieval, context_prepare, react_agent [EXTRACTED 1.00]
- **SQL Agent StateGraph Pipeline: list_tables → call_get_schema → get_schema → generate_query** — list_tables_node, call_get_schema_node, get_schema_node, generate_query_reactagent [EXTRACTED 1.00]

## Communities (13 total, 0 thin omitted)

### Community 0 - "Workflow Patterns: RAG & SQL Agent Concepts"
Cohesion: 0.13
Nodes (24): Spring Application Configuration (application.yml), call_get_schema LLM Node, Context Preparation (Prompt Formatting), DashScope API, EmbeddingModel (spring-ai-alibaba-starter-dashscope), generate_query ReactAgent Node, get_latest_news Tool, get_schema ToolNode (+16 more)

### Community 1 - "RAG Pipeline Nodes: Prepare, Retrieve & VectorStore"
Cohesion: 0.13
Nodes (15): Map, Object, OverAllState, Override, String, Map, Object, OverAllState (+7 more)

### Community 2 - "Application Entry & Agent Runners"
Cohesion: 0.12
Nodes (12): ApplicationListener, ApplicationReadyEvent, Environment, EventListener, RagAgentService, EventListener, SqlAgentService, Bean (+4 more)

### Community 3 - "SqlTools: SQL Database Tool Methods"
Cohesion: 0.24
Nodes (7): JdbcTemplate, String, Tool, List, ToolCallback, ToolCallbackResolver, SqlTools

### Community 4 - "RagAgentConfig: RAG Graph & Bean Wiring"
Cohesion: 0.32
Nodes (8): EmbeddingModel, Bean, ChatModel, CompiledGraph, RagAgentService, ReactAgent, VectorStore, RagAgentConfig

### Community 5 - "SqlAgentConfig: SQL Graph & Bean Wiring"
Cohesion: 0.33
Nodes (8): Bean, ChatModel, CompiledGraph, JdbcTemplate, ReactAgent, SqlAgentService, SqlTools, SqlAgentConfig

### Community 6 - "CallGetSchemaNode: Forced Schema Tool Invocation"
Cohesion: 0.25
Nodes (8): ChatModel, Map, Object, OverAllState, Override, SqlTools, String, CallGetSchemaNode

### Community 7 - "ListTablesNode: Deterministic Table Discovery"
Cohesion: 0.27
Nodes (7): Map, Object, OverAllState, Override, SqlTools, String, ListTablesNode

### Community 8 - "RewriteNode: LLM Query Rewriting"
Cohesion: 0.29
Nodes (7): ChatModel, Map, Object, OverAllState, Override, String, RewriteNode

### Community 9 - "RagAgentService: RAG Graph Execution"
Cohesion: 0.33
Nodes (4): CompiledGraph, String, RagAgentService, RagAgentResult

### Community 10 - "SqlAgentService: SQL Graph Execution"
Cohesion: 0.33
Nodes (4): CompiledGraph, String, SqlAgentService, SqlAgentResult

### Community 11 - "WorkflowAgentLoaderConfig: Studio Agent Registry"
Cohesion: 0.53
Nodes (4): AgentLoader, Bean, ReactAgent, WorkflowAgentLoaderConfig

### Community 12 - "RagAgentTools: News Retrieval Tool"
Cohesion: 0.50
Nodes (3): String, Tool, RagAgentTools

## Knowledge Gaps
- **32 isolated node(s):** `String`, `SqlAgentService`, `SqlAgentService`, `String`, `SqlAgentResult` (+27 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `List` connect `SqlTools: SQL Database Tool Methods` to `RAG Pipeline Nodes: Prepare, Retrieve & VectorStore`, `RagAgentConfig: RAG Graph & Bean Wiring`, `SqlAgentConfig: SQL Graph & Bean Wiring`, `CallGetSchemaNode: Forced Schema Tool Invocation`, `ListTablesNode: Deterministic Table Discovery`, `RagAgentService: RAG Graph Execution`, `SqlAgentService: SQL Graph Execution`, `WorkflowAgentLoaderConfig: Studio Agent Registry`?**
  _High betweenness centrality (0.311) - this node is a cross-community bridge._
- **Why does `RewriteNode` connect `RewriteNode: LLM Query Rewriting` to `RAG Pipeline Nodes: Prepare, Retrieve & VectorStore`?**
  _High betweenness centrality (0.040) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `SQL Agent Workflow` (e.g. with `RAG Agent Workflow` and `DashScope API`) actually correct?**
  _`SQL Agent Workflow` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `String`, `SqlAgentService`, `SqlAgentService` to the rest of the system?**
  _32 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Workflow Patterns: RAG & SQL Agent Concepts` be split into smaller, more focused modules?**
  _Cohesion score 0.13405797101449277 - nodes in this community are weakly interconnected._
- **Should `RAG Pipeline Nodes: Prepare, Retrieve & VectorStore` be split into smaller, more focused modules?**
  _Cohesion score 0.12857142857142856 - nodes in this community are weakly interconnected._
- **Should `Application Entry & Agent Runners` be split into smaller, more focused modules?**
  _Cohesion score 0.12380952380952381 - nodes in this community are weakly interconnected._