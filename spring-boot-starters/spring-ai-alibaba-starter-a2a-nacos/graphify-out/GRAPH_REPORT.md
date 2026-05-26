# Graph Report - /workspace/spring-boot-starters/spring-ai-alibaba-starter-a2a-nacos  (2026-05-26)

## Corpus Check
- Corpus is ~12,099 words - fits in a single context window. You may not need a graph.

## Summary
- 559 nodes · 1173 edges · 30 communities (25 shown, 5 thin omitted)
- Extraction: 88% EXTRACTED · 12% INFERRED · 0% AMBIGUOUS · INFERRED: 140 edges (avg confidence: 0.8)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Modes Url Interfaces|Modes Url Interfaces]]
- [[_COMMUNITY_Url Environment Server|Url Environment Server]]
- [[_COMMUNITY_Card Provider Client|Card Provider Client]]
- [[_COMMUNITY_Server Bean Conditional|Server Bean Conditional]]
- [[_COMMUNITY_Miscellaneous Components|Miscellaneous Components]]
- [[_COMMUNITY_Inet Jsonrpcerror Response|Inet Jsonrpcerror Response]]
- [[_COMMUNITY_Handler Server Executor|Handler Server Executor]]
- [[_COMMUNITY_Task Executor Execute|Task Executor Execute]]
- [[_COMMUNITY_Multi Handler Agents|Multi Handler Agents]]
- [[_COMMUNITY_Card Server Bean|Card Server Bean]]
- [[_COMMUNITY_Card Server Registry|Card Server Registry]]
- [[_COMMUNITY_Rpc Router Handler|Rpc Router Handler]]
- [[_COMMUNITY_Multi Router Rpc|Multi Router Rpc]]
- [[_COMMUNITY_Condition Outcome Client|Condition Outcome Client]]
- [[_COMMUNITY_Card Request Handler|Card Request Handler]]
- [[_COMMUNITY_Router Handler Provider|Router Handler Provider]]
- [[_COMMUNITY_Registry Service Bean|Registry Service Bean]]
- [[_COMMUNITY_Registry|Registry]]
- [[_COMMUNITY_Registry Service Register|Registry Service Register]]
- [[_COMMUNITY_Registry Bean Server|Registry Bean Server]]
- [[_COMMUNITY_Discovery Service Bean|Discovery Service Bean]]
- [[_COMMUNITY_Executor Server Provider|Executor Server Provider]]
- [[_COMMUNITY_Registry (2)|Registry (2)]]
- [[_COMMUNITY_Server|Server]]
- [[_COMMUNITY_Executor Server Provider (2)|Executor Server Provider (2)]]
- [[_COMMUNITY_Miscellaneous Components (2)|Miscellaneous Components (2)]]
- [[_COMMUNITY_Server Executor Provider|Server Executor Provider]]
- [[_COMMUNITY_Constants|Constants]]
- [[_COMMUNITY_Miscellaneous Components (3)|Miscellaneous Components (3)]]
- [[_COMMUNITY_Miscellaneous Components (4)|Miscellaneous Components (4)]]

## God Nodes (most connected - your core abstractions)
1. `A2aAgentCardProperties` - 29 edges
2. `NacosA2aProperties` - 22 edges
3. `String` - 18 edges
4. `String` - 17 edges
5. `AgentCardConverterUtil` - 16 edges
6. `A2aServerProperties` - 16 edges
7. `A2aServerMultiAgentAutoConfiguration` - 14 edges
8. `A2aServerMultiAgentAutoConfiguration - multi-agent server @AutoConfiguration (agent card list, handlers, router, registry)` - 12 edges
9. `List` - 11 edges
10. `A2aServerAgentCardAutoConfiguration` - 11 edges

## Surprising Connections (you probably didn't know these)
- `A2A Starter README - documents Nacos-integrated A2A server deployment and discovery` --documents--> `NacosA2aRegistryAutoConfiguration - @AutoConfiguration for Nacos A2A registry (A2aService + NacosA2aOperationService + NacosAgentRegistry)`  [INFERRED]
  README.md → src/main/java/com/alibaba/cloud/ai/a2a/autoconfigure/nacos/NacosA2aRegistryAutoConfiguration.java
- `A2A Starter README - documents Nacos-integrated A2A server deployment and discovery` --documents--> `NacosA2aDiscoveryAutoConfiguration - @AutoConfiguration for Nacos A2A service discovery (A2aService + NacosAgentCardProvider)`  [INFERRED]
  README.md → src/main/java/com/alibaba/cloud/ai/a2a/autoconfigure/nacos/NacosA2aDiscoveryAutoConfiguration.java
- `GraphAgentExecutor` --implements--> `AgentExecutor`  [EXTRACTED]
  main/java/com/alibaba/cloud/ai/a2a/core/server/GraphAgentExecutor.java → main/java/com/alibaba/cloud/ai/a2a/autoconfigure/server/A2aServerHandlerAutoConfiguration.java
- `JsonRpcA2aRequestHandler` --implements--> `A2aRequestHandler`  [EXTRACTED]
  main/java/com/alibaba/cloud/ai/a2a/core/server/JsonRpcA2aRequestHandler.java → main/java/com/alibaba/cloud/ai/a2a/core/server/A2aRequestHandler.java
- `OnMultiAgentModeCondition - SpringBootCondition detecting agents.* properties in environment` --checks_prefix_from_config_in_environment--> `A2aMultiAgentProperties - @ConfigurationProperties for multi-agent mode with agents map`  [INFERRED]
  src/main/java/com/alibaba/cloud/ai/a2a/autoconfigure/server/condition/OnMultiAgentModeCondition.java → src/main/java/com/alibaba/cloud/ai/a2a/autoconfigure/A2aMultiAgentProperties.java

## Hyperedges (group relationships)
- **Single-Agent Auto-Configuration Chain** — A2aServerAgentCardAutoConfiguration_autoconfig, A2aServerHandlerAutoConfiguration_autoconfig, A2aServerAutoConfiguration_autoconfig, A2aServerRegistryAutoConfiguration_autoconfig [INFERRED 0.85]
- **Multi-Agent Auto-Configuration Flow** — A2aServerMultiAgentAutoConfiguration_autoconfig, OnMultiAgentModeCondition_condition, A2aMultiAgentProperties_config, AgentRegistryService_service, MultiAgentJsonRpcRouterProvider_router [INFERRED 0.85]
- **Nacos Service Registry and Discovery Integration** — NacosA2aDiscoveryAutoConfiguration_autoconfig, NacosA2aRegistryAutoConfiguration_autoconfig, A2aServerProperties_config, AgentRegistry_interface [INFERRED 0.85]
- **A2A Server Request Processing Pipeline** — MultiAgentRequestRouter_MultiAgentRequestRouter, JsonRpcA2aRequestHandler_JsonRpcA2aRequestHandler, A2aRequestHandler_A2aRequestHandler, GraphAgentExecutor_GraphAgentExecutor, GraphAgentExecutor_ReactAgentNodeOutputConsumer, ServerTypeEnum_ServerTypeEnum [INFERRED 0.85]
- **Nacos Registry and Discovery Architecture** — NacosAgentRegistry_NacosAgentRegistry, NacosA2aOperationService_NacosA2aOperationService, NacosAgentCardProvider_NacosAgentCardProvider, NacosAgentCardWrapper_NacosAgentCardWrapper, AgentCardConverterUtil_AgentCardConverterUtil, NacosA2aProperties_NacosA2aProperties, NacosA2aRegistryProperties_NacosA2aRegistryProperties [INFERRED 0.85]
- **Spring Boot Configuration Properties Bindings** — NacosA2aProperties_NacosA2aProperties, NacosA2aRegistryProperties_NacosA2aRegistryProperties, additional-spring-configuration-metadata [EXTRACTED 1.00]

## Communities (30 total, 5 thin omitted)

### Community 0 - "Modes Url Interfaces"
Cohesion: 0.07
Nodes (25): A2aAgentCardProperties, AgentCapabilities, AgentInterface, AgentProvider, AgentSkill, List, Map, SecurityScheme (+17 more)

### Community 1 - "Url Environment Server"
Cohesion: 0.08
Nodes (21): A2aServerProperties, EnvironmentAware, Integer, Environment, Override, String, A2aServerProperties, Bean (+13 more)

### Community 2 - "Card Provider Client"
Cohesion: 0.09
Nodes (19): A2aAgentCardProperties, A2aClientAgentCardProperties, A2aClientAgentCardProperties, A2aServerAgentCardProperties, A2aClientAgentCardProviderAutoConfiguration, Conditional, ConditionalOnClass, NacosAgentCardProvider (+11 more)

### Community 3 - "Server Bean Conditional"
Cohesion: 0.14
Nodes (24): A2aAgentCardProperties, A2aServerExecutorProvider, A2aServerProperties, Agent, AgentCard, AgentInterface, AgentRegistry, AgentRegistryService (+16 more)

### Community 4 - "Miscellaneous Components"
Cohesion: 0.12
Nodes (10): Environment, Map, Object, Override, String, Properties, NacosA2aProperties, PropertyResolver (+2 more)

### Community 5 - "Inet Jsonrpcerror Response"
Cohesion: 0.12
Nodes (17): Boolean, Function, InetAddress, JSONRPCError, JSONRPCErrorResponse, JSONRPCRequest, JSONRPCResponse, AgentCard (+9 more)

### Community 6 - "Handler Server Executor"
Cohesion: 0.21
Nodes (15): A2aServerExecutorProvider, Agent, AgentCard, AgentExecutor, Bean, ConditionalOnMissingBean, ConditionalOnProperty, JsonRpcA2aRequestHandler (+7 more)

### Community 7 - "Task Executor Execute"
Cohesion: 0.19
Nodes (12): EventQueue, Agent, Override, String, Message, NodeOutput, RequestContext, RunnableConfig (+4 more)

### Community 8 - "Multi Handler Agents"
Cohesion: 0.13
Nodes (11): A2aMultiAgentProperties, A2aMultiAgentProperties, A2aAgentCardProperties, Map, String, JsonRpcA2aRequestHandler, String, MultiAgentRequestRouter (+3 more)

### Community 9 - "Card Server Bean"
Cohesion: 0.25
Nodes (13): A2aServerAgentCardProperties, A2aServerProperties, Agent, AgentCapabilities, AgentCard, AgentInterface, AgentSkill, Bean (+5 more)

### Community 10 - "Card Server Registry"
Cohesion: 0.20
Nodes (22): A2aAgentCardProperties - base agent card properties model (name, description, url, capabilities, skills, security), A2aClientAgentCardProperties - @ConfigurationProperties extending A2aAgentCardProperties for client card, A2aClientAgentCardProviderAutoConfiguration - @AutoConfiguration for client AgentCardProvider beans (remote + local), A2aClientAgentCardWellKnownCondition - SpringBootCondition matching when wellKnownUrl is set, A2aConstants - protocol constants (DEFAULT_A2A_PROTOCOL_VERSION, transport types, agent version), A2aMultiAgentProperties - @ConfigurationProperties for multi-agent mode with agents map, A2aRouterProvider<S> - generic interface for A2A router providers, A2aServerAgentCardAutoConfiguration - single-agent AgentCard builder @AutoConfiguration from properties and Agent bean (+14 more)

### Community 11 - "Rpc Router Handler"
Cohesion: 0.18
Nodes (11): Flux, JsonRpcA2aRequestHandler, Object, Override, RouterFunction, ServerRequest, ServerResponse, String (+3 more)

### Community 12 - "Multi Router Rpc"
Cohesion: 0.17
Nodes (11): Flux, MultiAgentRequestRouter, Object, Override, RouterFunction, ServerRequest, ServerResponse, String (+3 more)

### Community 13 - "Condition Outcome Client"
Cohesion: 0.19
Nodes (12): A2aClientAgentCardWellKnownCondition, OnMultiAgentModeCondition, AnnotatedTypeMetadata, ConditionContext, ConditionOutcome, Override, AnnotatedTypeMetadata, ConditionContext (+4 more)

### Community 14 - "Card Request Handler"
Cohesion: 0.16
Nodes (14): A2aRequestHandler, A2aServerMultiAgentAutoConfigurationTest, AgentCardConverterUtilTest, AgentCardConverterUtil, GraphAgentExecutor, ReactAgentNodeOutputConsumer, JsonRpcA2aRequestHandler, MultiAgentRequestRouter (+6 more)

### Community 15 - "Router Handler Provider"
Cohesion: 0.18
Nodes (9): RouterFunction, ServerResponse, AgentCard, Headers, Object, String, A2aRouterProvider, S (+1 more)

### Community 16 - "Registry Service Bean"
Cohesion: 0.33
Nodes (9): A2aServerProperties, A2aService, Bean, ConditionalOnMissingBean, NacosA2aOperationService, NacosA2aProperties, NacosA2aRegistryProperties, NacosA2aRegistryAutoConfiguration (+1 more)

### Community 17 - "Registry"
Cohesion: 0.27
Nodes (7): AgentRegistry, AgentCard, NacosA2aOperationService, NacosA2aProperties, Override, String, NacosAgentRegistry

### Community 18 - "Registry Service Register"
Cohesion: 0.36
Nodes (5): EventListener, AgentCard, AgentRegistry, List, AgentRegistryService

### Community 19 - "Registry Bean Server"
Cohesion: 0.39
Nodes (7): AgentCard, AgentRegistry, AgentRegistryService, Bean, ConditionalOnBean, ConditionalOnMissingBean, A2aServerRegistryAutoConfiguration

### Community 20 - "Discovery Service Bean"
Cohesion: 0.42
Nodes (6): A2aService, Bean, ConditionalOnMissingBean, NacosA2aProperties, NacosA2aDiscoveryAutoConfiguration, NacosAgentCardProvider

### Community 21 - "Executor Server Provider"
Cohesion: 0.28
Nodes (5): A2aServerExecutorProvider, ExecutorService, Override, PreDestroy, DefaultA2aServerExecutorProvider

### Community 22 - "Registry (2)"
Cohesion: 0.40
Nodes (3): AgentCard, String, AgentRegistry

### Community 23 - "Server"
Cohesion: 0.80
Nodes (4): String, getType(), ServerTypeEnum(), valueOfType()

### Community 25 - "Miscellaneous Components (2)"
Cohesion: 0.50
Nodes (3): groups, hints, properties

## Knowledge Gaps
- **35 isolated node(s):** `String`, `Object`, `Override`, `String`, `String` (+30 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **5 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `AgentExecutor` connect `Handler Server Executor` to `Server Bean Conditional`, `Task Executor Execute`?**
  _High betweenness centrality (0.125) - this node is a cross-community bridge._
- **Why does `JSONRPCResponse` connect `Inet Jsonrpcerror Response` to `Rpc Router Handler`, `Multi Router Rpc`?**
  _High betweenness centrality (0.074) - this node is a cross-community bridge._
- **What connects `String`, `Object`, `Override` to the rest of the system?**
  _35 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Modes Url Interfaces` be split into smaller, more focused modules?**
  _Cohesion score 0.0671484492622704 - nodes in this community are weakly interconnected._
- **Should `Url Environment Server` be split into smaller, more focused modules?**
  _Cohesion score 0.07922705314009662 - nodes in this community are weakly interconnected._
- **Should `Card Provider Client` be split into smaller, more focused modules?**
  _Cohesion score 0.08771929824561403 - nodes in this community are weakly interconnected._
- **Should `Server Bean Conditional` be split into smaller, more focused modules?**
  _Cohesion score 0.1422475106685633 - nodes in this community are weakly interconnected._