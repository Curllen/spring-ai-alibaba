# Graph Report - /workspace/spring-boot-starters/spring-ai-alibaba-starter-config-nacos  (2026-05-27)

## Corpus Check
- Corpus is ~13,092 words - fits in a single context window. You may not need a graph.

## Summary
- 535 nodes · 1192 edges · 22 communities (19 shown, 3 thin omitted)
- Extraction: 89% EXTRACTED · 11% INFERRED · 0% AMBIGUOUS · INFERRED: 129 edges (avg confidence: 0.8)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Interceptor Test Hook Tools|Interceptor Test Hook Tools]]
- [[_COMMUNITY_MCP Gateway Tool Definition Initializer|MCP Gateway Tool Definition Initializer]]
- [[_COMMUNITY_Agent Builder Injector Pipeline|Agent Builder Injector Pipeline]]
- [[_COMMUNITY_VO Factory Class Definitions|VO Factory Class Definitions]]
- [[_COMMUNITY_Tools Test Resolver Callback|Tools Test Resolver Callback]]
- [[_COMMUNITY_Nacos Options Config Service|Nacos Options Config Service]]
- [[_COMMUNITY_Prompt Builder Observation Config|Prompt Builder Observation Config]]
- [[_COMMUNITY_Model Prompt VO Accessors|Model Prompt VO Accessors]]
- [[_COMMUNITY_MCP Gateway Tool Callback|MCP Gateway Tool Callback]]
- [[_COMMUNITY_Context Holder State Container|Context Holder State Container]]
- [[_COMMUNITY_Tools Integration Test Suite|Tools Integration Test Suite]]
- [[_COMMUNITY_MCP Servers VO Config|MCP Servers VO Config]]
- [[_COMMUNITY_MCP Gateway Abstract Definition|MCP Gateway Abstract Definition]]
- [[_COMMUNITY_Chat Options CGLIB Proxy|Chat Options CGLIB Proxy]]
- [[_COMMUNITY_Agent Config Bean Registration|Agent Config Bean Registration]]
- [[_COMMUNITY_Partner Agents VO Config|Partner Agents VO Config]]
- [[_COMMUNITY_Memory VO Storage Config|Memory VO Storage Config]]
- [[_COMMUNITY_Model Injector Unsafe Reflection|Model Injector Unsafe Reflection]]
- [[_COMMUNITY_MCP Tools Injector Convert|MCP Tools Injector Convert]]
- [[_COMMUNITY_Partner Agents Injector Registry|Partner Agents Injector Registry]]
- [[_COMMUNITY_Agent VO Accessors|Agent VO Accessors]]
- [[_COMMUNITY_Memory VO Singleton|Memory VO Singleton]]

## God Nodes (most connected - your core abstractions)
1. `NacosOptions` - 27 edges
2. `NacosReactAgentBuilderToolsTest` - 24 edges
3. `NacosMcpGatewayToolDefinition` - 24 edges
4. `NacosReactAgentBuilderInterceptorTest` - 20 edges
5. `NacosReactAgentBuilder - 核心Agent构建器` - 19 edges
6. `String` - 16 edges
7. `Test` - 15 edges
8. `NacosContextHolder` - 15 edges
9. `McpGatewayToolDefinition` - 15 edges
10. `NacosOptions - Nacos配置选项容器` - 14 edges

## Surprising Connections (you probably didn't know these)
- `README - 项目说明文档` --references--> `NacosReactAgentBuilder - 核心Agent构建器`  [INFERRED]
  spring-boot-starters/spring-ai-alibaba-starter-config-nacos/README.md → spring-boot-starters/spring-ai-alibaba-starter-config-nacos/src/main/java/com/alibaba/cloud/ai/agent/nacos/NacosReactAgentBuilder.java
- `NacosOptions - Nacos配置选项容器` --references--> `NacosConfigService`  [EXTRACTED]
  spring-boot-starters/spring-ai-alibaba-starter-config-nacos/src/main/java/com/alibaba/cloud/ai/agent/nacos/NacosOptions.java → main/java/com/alibaba/cloud/ai/agent/nacos/NacosOptions.java
- `NacosOptions - Nacos配置选项容器` --references--> `AiMaintainerService`  [EXTRACTED]
  spring-boot-starters/spring-ai-alibaba-starter-config-nacos/src/main/java/com/alibaba/cloud/ai/agent/nacos/NacosOptions.java → main/java/com/alibaba/cloud/ai/agent/nacos/NacosOptions.java
- `NacosAgentConfig - Spring自动配置类` --semantically_similar_to--> `ChatOptionsProxy - CGLIB动态代理创建ChatOptions`  [INFERRED] [semantically similar]
  spring-boot-starters/spring-ai-alibaba-starter-config-nacos/src/main/java/com/alibaba/cloud/ai/agent/nacos/config/NacosAgentConfig.java → spring-boot-starters/spring-ai-alibaba-starter-config-nacos/src/main/java/com/alibaba/cloud/ai/agent/nacos/utils/ChatOptionsProxy.java
- `NacosReactAgentBuilder` --inherits--> `NacosAgentPromptBuilder`  [EXTRACTED]
  main/java/com/alibaba/cloud/ai/agent/nacos/NacosReactAgentBuilder.java → main/java/com/alibaba/cloud/ai/agent/nacos/NacosAgentPromptBuilder.java

## Communities (22 total, 3 thin omitted)

### Community 0 - "Interceptor Test Hook Tools"
Cohesion: 0.09
Nodes (25): ModelCallHandler, ModelInterceptor, ModelRequest, ModelResponse, EchoFunction, NacosReactAgentBuilderInterceptorTest, TestHookWithTools, TestModelInterceptor (+17 more)

### Community 1 - "MCP Gateway Tool Definition Initializer"
Cohesion: 0.07
Nodes (16): Boolean, Builder, McpServerRemoteServiceConfig, Object, Override, String, List, McpServerVO (+8 more)

### Community 2 - "Agent Builder Injector Pipeline"
Cohesion: 0.08
Nodes (27): AbstractListener, AgentVO, NacosOptions, ModelVO, NacosOptions, NacosOptions, PromptVO, String (+19 more)

### Community 3 - "VO Factory Class Definitions"
Cohesion: 0.08
Nodes (37): AgentBaseListener - Agent基础配置变更监听器, AgentVO - Agent配置值对象, ChatOptionsProxy - CGLIB动态代理创建ChatOptions, McpGatewayToolDefinition - MCP网关工具定义抽象类, McpServersVO - MCP服务器配置值对象, ModelVO - 模型配置值对象, NacosAgentBuilderFactory - ReactAgent Builder工厂, NacosAgentConfig - Spring自动配置类 (+29 more)

### Community 4 - "Tools Test Resolver Callback"
Cohesion: 0.12
Nodes (16): Hook, EchoFunction, SimpleToolCallbackResolver, TestHookWithTools, TestToolClass, AgentToolNode, BeforeEach, List (+8 more)

### Community 5 - "Nacos Options Config Service"
Cohesion: 0.10
Nodes (7): AiMaintainerService, NacosMcpOperationService, ObservationConfiguration, Properties, String, NacosOptions, NacosConfigService

### Community 6 - "Prompt Builder Observation Config"
Cohesion: 0.13
Nodes (14): DefaultBuilder, Map, NacosOptions, ObservationMetadataAwareOptions, Override, PromptVO, ReactAgent, String (+6 more)

### Community 7 - "Model Prompt VO Accessors"
Cohesion: 0.14
Nodes (5): String, List, String, ModelVO, PromptVO

### Community 8 - "MCP Gateway Tool Callback"
Cohesion: 0.14
Nodes (14): Map, McpGatewayToolDefinition, McpServerRemoteServiceConfig, McpServerVO, NacosMcpOperationService, Object, Override, String (+6 more)

### Community 9 - "Context Holder State Container"
Cohesion: 0.13
Nodes (10): AgentVO, Map, McpServersVO, ModelVO, ObservationMetadataAwareOptions, PromptVO, ReactAgent, String (+2 more)

### Community 10 - "Tools Integration Test Suite"
Cohesion: 0.42
Nodes (3): NacosReactAgentBuilderToolsTest, AgentLlmNode, Test

### Community 11 - "MCP Servers VO Config"
Cohesion: 0.19
Nodes (7): List, Map, McpServerVO, String, Set, McpServersVO, McpServerVO

### Community 12 - "MCP Gateway Abstract Definition"
Cohesion: 0.18
Nodes (5): Boolean, Object, String, ToolDefinition, McpGatewayToolDefinition

### Community 13 - "Chat Options CGLIB Proxy"
Cohesion: 0.24
Nodes (10): ChatOptions, Map, Object, Override, String, Method, MethodInterceptor, MethodProxy (+2 more)

### Community 14 - "Agent Config Bean Registration"
Cohesion: 0.27
Nodes (11): Bean, NacosAgentConfig, ConfigurableEnvironment, ChatClientObservationConvention, ChatModelObservationConvention, NacosOptions, ObservationConfiguration, ObservationRegistry (+3 more)

### Community 15 - "Partner Agents VO Config"
Cohesion: 0.25
Nodes (6): List, Map, String, PartnerAgentVO, PartnerAgentsVO, PartnerAgentVO

### Community 17 - "Model Injector Unsafe Reflection"
Cohesion: 0.32
Nodes (7): Field, ChatClient, ChatModel, Object, OpenAiChatOptions, String, NacosModelInjector

### Community 18 - "MCP Tools Injector Convert"
Cohesion: 0.36
Nodes (5): List, McpServersVO, NacosOptions, ToolCallback, NacosMcpToolsInjector

### Community 19 - "Partner Agents Injector Registry"
Cohesion: 0.36
Nodes (6): AgentLlmNode, AgentToolNode, NacosOptions, String, NacosPartnerAgentsInjector, PartnerAgentsVO

## Knowledge Gaps
- **20 isolated node(s):** `NacosOptions`, `NacosOptions`, `NacosOptions`, `NacosOptions`, `Override` (+15 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **3 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `McpServersVO - MCP服务器配置值对象` connect `VO Factory Class Definitions` to `Interceptor Test Hook Tools`, `MCP Gateway Tool Definition Initializer`, `Agent Builder Injector Pipeline`, `Tools Test Resolver Callback`, `MCP Gateway Tool Callback`?**
  _High betweenness centrality (0.132) - this node is a cross-community bridge._
- **Why does `NacosOptions` connect `Nacos Options Config Service` to `Agent Builder Injector Pipeline`, `MCP Tools Injector Convert`?**
  _High betweenness centrality (0.091) - this node is a cross-community bridge._
- **Why does `NacosConfigService` connect `Nacos Options Config Service` to `Interceptor Test Hook Tools`, `Agent Builder Injector Pipeline`, `VO Factory Class Definitions`, `Tools Test Resolver Callback`?**
  _High betweenness centrality (0.080) - this node is a cross-community bridge._
- **What connects `NacosOptions`, `NacosOptions`, `NacosOptions` to the rest of the system?**
  _20 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Interceptor Test Hook Tools` be split into smaller, more focused modules?**
  _Cohesion score 0.08771929824561403 - nodes in this community are weakly interconnected._
- **Should `MCP Gateway Tool Definition Initializer` be split into smaller, more focused modules?**
  _Cohesion score 0.07239819004524888 - nodes in this community are weakly interconnected._
- **Should `Agent Builder Injector Pipeline` be split into smaller, more focused modules?**
  _Cohesion score 0.08235294117647059 - nodes in this community are weakly interconnected._