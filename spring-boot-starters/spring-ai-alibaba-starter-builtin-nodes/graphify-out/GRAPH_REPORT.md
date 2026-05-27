# Graph Report - /workspace/spring-boot-starters/spring-ai-alibaba-starter-builtin-nodes  (2026-05-27)

## Corpus Check
- Corpus is ~34,603 words - fits in a single context window. You may not need a graph.

## Summary
- 939 nodes · 2139 edges · 42 communities (37 shown, 5 thin omitted)
- Extraction: 85% EXTRACTED · 15% INFERRED · 0% AMBIGUOUS · INFERRED: 312 edges (avg confidence: 0.79)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Built-in Nodes Core Overview|Built-in Nodes Core Overview]]
- [[_COMMUNITY_Knowledge Retrieval Builder Config|Knowledge Retrieval Builder Config]]
- [[_COMMUNITY_Code Execution Node Action|Code Execution Node Action]]
- [[_COMMUNITY_Template Transform Variable Tests|Template Transform Variable Tests]]
- [[_COMMUNITY_Iteration Node Loop Flow|Iteration Node Loop Flow]]
- [[_COMMUNITY_Tool Node Message Conversion|Tool Node Message Conversion]]
- [[_COMMUNITY_LLM Node Chat Client|LLM Node Chat Client]]
- [[_COMMUNITY_Parameter Parsing Chat LLM|Parameter Parsing Chat LLM]]
- [[_COMMUNITY_List Operator Filter Sort|List Operator Filter Sort]]
- [[_COMMUNITY_Variable Aggregator Groups|Variable Aggregator Groups]]
- [[_COMMUNITY_Code Template Transformer Hierarchy|Code Template Transformer Hierarchy]]
- [[_COMMUNITY_Assigner Node Write Mode|Assigner Node Write Mode]]
- [[_COMMUNITY_Http Node Test Suite|Http Node Test Suite]]
- [[_COMMUNITY_MCP Node Exception Handler|MCP Node Exception Handler]]
- [[_COMMUNITY_Agent Node Strategy Config|Agent Node Strategy Config]]
- [[_COMMUNITY_Code Execution Config Timeout|Code Execution Config Timeout]]
- [[_COMMUNITY_Document Extractor File Parser|Document Extractor File Parser]]
- [[_COMMUNITY_Question Classifier Categories|Question Classifier Categories]]
- [[_COMMUNITY_Template Transform Core Methods|Template Transform Core Methods]]
- [[_COMMUNITY_Http Node Core Implementation|Http Node Core Implementation]]
- [[_COMMUNITY_Http Node Body Multipart|Http Node Body Multipart]]
- [[_COMMUNITY_Code Entities Definitions|Code Entities Definitions]]
- [[_COMMUNITY_Local Code Executor Command|Local Code Executor Command]]
- [[_COMMUNITY_Docker Code Executor Container|Docker Code Executor Container]]
- [[_COMMUNITY_Answer Node Output|Answer Node Output]]
- [[_COMMUNITY_File Storage In Memory|File Storage In Memory]]
- [[_COMMUNITY_Test POJOs User Address|Test POJOs User Address]]
- [[_COMMUNITY_File Utils Jar Copy|File Utils Jar Copy]]
- [[_COMMUNITY_Http Request Body Type|Http Request Body Type]]
- [[_COMMUNITY_Http Auth Config Type|Http Auth Config Type]]
- [[_COMMUNITY_Code Executor Interface|Code Executor Interface]]
- [[_COMMUNITY_Http Node Builder Config|Http Node Builder Config]]
- [[_COMMUNITY_Docker Executor CI Test|Docker Executor CI Test]]
- [[_COMMUNITY_Code Utils Language Mapping|Code Utils Language Mapping]]
- [[_COMMUNITY_Http Retry Config|Http Retry Config]]
- [[_COMMUNITY_Code Execution Result|Code Execution Result]]
- [[_COMMUNITY_Utils Class Definitions|Utils Class Definitions]]

## God Nodes (most connected - your core abstractions)
1. `TemplateTransformNodeTest` - 38 edges
2. `Test` - 38 edges
3. `NodeAction` - 36 edges
4. `OverAllState` - 35 edges
5. `String` - 27 edges
6. `Builder` - 25 edges
7. `String` - 23 edges
8. `ElementInput` - 23 edges
9. `CodeExecutionConfig` - 21 edges
10. `ElementOutput` - 18 edges

## Surprising Connections (you probably didn't know these)
- `HttpNodeTest` --calls--> `MockWebServer`  [EXTRACTED]
  src/test/java/com/alibaba/cloud/ai/graph/node/HttpNodeTest.java → external/okhttp3.mockwebserver
- `TemplateTransformNodeTest` --calls--> `TestAddress`  [EXTRACTED]
  src/test/java/com/alibaba/cloud/ai/graph/node/TemplateTransformNodeTest.java → test/java/com/alibaba/cloud/ai/graph/node/TemplateTransformNodeTest.java
- `AssignerNode` --implements--> `NodeAction`  [EXTRACTED]
  main/java/com/alibaba/cloud/ai/graph/node/AssignerNode.java → test/java/com/alibaba/cloud/ai/graph/node/IterationNodeTest.java
- `HttpNode` --implements--> `NodeAction`  [EXTRACTED]
  main/java/com/alibaba/cloud/ai/graph/node/HttpNode.java → test/java/com/alibaba/cloud/ai/graph/node/IterationNodeTest.java
- `AnswerNode` --implements--> `NodeAction`  [EXTRACTED]
  main/java/com/alibaba/cloud/ai/graph/node/AnswerNode.java → test/java/com/alibaba/cloud/ai/graph/node/IterationNodeTest.java

## Communities (42 total, 5 thin omitted)

### Community 0 - "Built-in Nodes Core Overview"
Cohesion: 0.05
Nodes (59): AgentNode - Agent智能体节点, AnswerNode - 答案渲染节点, AssignerNode - 变量赋值节点, HttpNode, HttpNodeTest, HumanNode - 人工干预节点(已注释/废弃), InMemoryFileStorage, IterationNode - 迭代循环节点 (+51 more)

### Community 1 - "Knowledge Retrieval Builder Config"
Cohesion: 0.07
Nodes (23): DocumentExtractorNode - 文档提取节点, KnowledgeRetrievalNode - 知识检索节点, DashScopeRerankOptions, Document, DocumentPostProcessor, Double, Expression, Boolean (+15 more)

### Community 2 - "Code Execution Node Action"
Cohesion: 0.07
Nodes (33): Builder, CodeExecutorNodeAction, CodeActionTest, CodeExecutionConfig, CodeExecutorNodeAction, CodeLanguage, CodeParam, DockerCodeExecutor (+25 more)

### Community 3 - "Template Transform Variable Tests"
Cohesion: 0.11
Nodes (10): TemplateTransformNodeTest, VariableAggregatorNodeTest, String, Test, BeforeEach, List, Map, Object (+2 more)

### Community 4 - "Iteration Node Loop Flow"
Cohesion: 0.12
Nodes (18): ElementInput, ElementOutput, Map, Object, OverAllState, Override, String, Builder (+10 more)

### Community 5 - "Tool Node Message Conversion"
Cohesion: 0.08
Nodes (24): ToolNode - 工具调用节点, AssistantMessage, JsonNode, Builder, List, Map, Object, OverAllState (+16 more)

### Community 6 - "LLM Node Chat Client"
Cohesion: 0.11
Nodes (17): Advisor, ChatClientRequestSpec, ChatResponse, Flux, Boolean, Builder, ChatClient, List (+9 more)

### Community 7 - "Parameter Parsing Chat LLM"
Cohesion: 0.11
Nodes (18): Builder, ChatClient, List, Map, Object, OverAllState, Override, String (+10 more)

### Community 8 - "List Operator Filter Sort"
Cohesion: 0.12
Nodes (19): Class, Comparator, Long, Integer, Map, Object, OverAllState, Override (+11 more)

### Community 9 - "Variable Aggregator Groups"
Cohesion: 0.12
Nodes (12): AdvancedSettings, Group, List, Map, Object, OverAllState, Override, String (+4 more)

### Community 10 - "Code Template Transformer Hierarchy"
Cohesion: 0.12
Nodes (18): TemplateTransformer, JavaTemplateTransformer, NodeJsTemplateTransformer, CodeStyle, Override, String, CodeStyle, Override (+10 more)

### Community 11 - "Assigner Node Write Mode"
Cohesion: 0.14
Nodes (13): Builder, List, Map, Object, OverAllState, Override, String, AssignerNode (+5 more)

### Community 12 - "Http Node Test Suite"
Cohesion: 0.15
Nodes (10): AfterEach, AuthConfig, HttpMethod, HttpNodeTest, HttpRequestNodeBody, InMemoryFileStorage, MockWebServer, HttpNodeTest (+2 more)

### Community 13 - "MCP Node Exception Handler"
Cohesion: 0.15
Nodes (12): Builder, List, Map, Object, OverAllState, Override, String, Builder (+4 more)

### Community 14 - "Agent Node Strategy Config"
Cohesion: 0.14
Nodes (13): Builder, ChatClient, Integer, List, Map, Object, OverAllState, Override (+5 more)

### Community 15 - "Code Execution Config Timeout"
Cohesion: 0.12
Nodes (3): CodeExecutionConfig, String, BeforeEach

### Community 16 - "Document Extractor File Parser"
Cohesion: 0.17
Nodes (10): InputStream, Builder, List, Map, Object, OverAllState, Override, String (+2 more)

### Community 17 - "Question Classifier Categories"
Cohesion: 0.18
Nodes (11): Deprecated, Builder, ChatClient, List, Map, Object, OverAllState, Override (+3 more)

### Community 18 - "Template Transform Core Methods"
Cohesion: 0.21
Nodes (8): Builder, Map, Object, OverAllState, Override, String, Builder, TemplateTransformNode

### Community 19 - "Http Node Core Implementation"
Cohesion: 0.19
Nodes (9): Function, HttpHeaders, Builder, Map, Object, OverAllState, Override, HttpNode (+1 more)

### Community 20 - "Http Node Body Multipart"
Cohesion: 0.22
Nodes (4): String, BodyData, from(), RequestBodySpec

### Community 21 - "Code Entities Definitions"
Cohesion: 0.31
Nodes (17): CodeBlock, CodeExecutionConfig, CodeExecutionResult, CodeExecutorNodeAction, CodeExecutor (Interface), CodeLanguage (Enum), CodeParam, CodeStyle (Enum) (+9 more)

### Community 22 - "Local Code Executor Command"
Cohesion: 0.18
Nodes (10): LocalCommandlineCodeExecutor, CodeExecutor, FileUtils, FileUtilsTest, CodeBlock, CodeExecutionConfig, CodeExecutionResult, List (+2 more)

### Community 23 - "Docker Code Executor Container"
Cohesion: 0.22
Nodes (9): DockerCodeExecutor, LogContainerResultCallback, Frame, CodeBlock, CodeExecutionConfig, CodeExecutionResult, List, Override (+1 more)

### Community 24 - "Answer Node Output"
Cohesion: 0.19
Nodes (8): Builder, Map, Object, OverAllState, Override, String, AnswerNode, Builder

### Community 25 - "File Storage In Memory"
Cohesion: 0.21
Nodes (3): String, FileRecord, InMemoryFileStorage

### Community 26 - "Test POJOs User Address"
Cohesion: 0.21
Nodes (4): TestAddress, TestUser, String, TestAddress

### Community 27 - "File Utils Jar Copy"
Cohesion: 0.29
Nodes (4): ClassLoader, Path, String, FileUtils

### Community 28 - "Http Request Body Type"
Cohesion: 0.26
Nodes (4): BodyData, BodyType, List, HttpRequestNodeBody

### Community 30 - "Code Executor Interface"
Cohesion: 0.39
Nodes (5): CodeExecutor, CodeBlock, CodeExecutionConfig, CodeExecutionResult, List

### Community 31 - "Http Node Builder Config"
Cohesion: 0.25
Nodes (3): Builder, RetryConfig, WebClient

### Community 32 - "Docker Executor CI Test"
Cohesion: 0.40
Nodes (3): DockerCodeExecutorTest, EnabledIf, Test

## Ambiguous Edges - Review These
- `HumanNode - 人工干预节点(已注释/废弃)` → `HumanNode - 人工干预节点(已注释/废弃)`  [AMBIGUOUS]
  spring-boot-starters/spring-ai-alibaba-starter-builtin-nodes/src/main/java/com/alibaba/cloud/ai/graph/node/HumanNode.java · relation: conceptually_related_to
- `CodeExecutorNodeAction` → `LocalCommandlineCodeExecutor`  [AMBIGUOUS]
  spring-boot-starters/spring-ai-alibaba-starter-builtin-nodes/src/main/java/com/alibaba/cloud/ai/graph/node/code/CodeExecutorNodeAction.java · relation: calls
- `CodeExecutorNodeAction` → `DockerCodeExecutor`  [AMBIGUOUS]
  spring-boot-starters/spring-ai-alibaba-starter-builtin-nodes/src/main/java/com/alibaba/cloud/ai/graph/node/code/CodeExecutorNodeAction.java · relation: calls
- `Messageutils` → `InMemoryFileStorage`  [AMBIGUOUS]
  spring-boot-starters/spring-ai-alibaba-starter-builtin-nodes/src/main/java/com/alibaba/cloud/ai/graph/utils/Messageutils.java · relation: conceptually_related_to

## Knowledge Gaps
- **69 isolated node(s):** `String`, `Object`, `String`, `String`, `Object` (+64 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **5 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **What is the exact relationship between `HumanNode - 人工干预节点(已注释/废弃)` and `HumanNode - 人工干预节点(已注释/废弃)`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **What is the exact relationship between `CodeExecutorNodeAction` and `LocalCommandlineCodeExecutor`?**
  _Edge tagged AMBIGUOUS (relation: calls) - confidence is low._
- **What is the exact relationship between `CodeExecutorNodeAction` and `DockerCodeExecutor`?**
  _Edge tagged AMBIGUOUS (relation: calls) - confidence is low._
- **What is the exact relationship between `Messageutils` and `InMemoryFileStorage`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **Why does `NodeAction` connect `Iteration Node Loop Flow` to `Knowledge Retrieval Builder Config`, `Code Execution Node Action`, `Tool Node Message Conversion`, `LLM Node Chat Client`, `Parameter Parsing Chat LLM`, `List Operator Filter Sort`, `Variable Aggregator Groups`, `Assigner Node Write Mode`, `MCP Node Exception Handler`, `Agent Node Strategy Config`, `Document Extractor File Parser`, `Question Classifier Categories`, `Template Transform Core Methods`, `Http Node Core Implementation`, `Answer Node Output`?**
  _High betweenness centrality (0.375) - this node is a cross-community bridge._
- **Why does `OverAllState` connect `Built-in Nodes Core Overview` to `Code Execution Node Action`, `Template Transform Variable Tests`, `Iteration Node Loop Flow`, `List Operator Filter Sort`, `Assigner Node Write Mode`, `Http Node Test Suite`?**
  _High betweenness centrality (0.118) - this node is a cross-community bridge._
- **Why does `ObjectMapper` connect `Built-in Nodes Core Overview` to `Iteration Node Loop Flow`, `Tool Node Message Conversion`, `Parameter Parsing Chat LLM`, `List Operator Filter Sort`, `Code Template Transformer Hierarchy`, `Template Transform Core Methods`, `Http Node Core Implementation`?**
  _High betweenness centrality (0.045) - this node is a cross-community bridge._