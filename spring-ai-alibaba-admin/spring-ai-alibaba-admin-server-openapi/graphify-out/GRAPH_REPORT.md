# Graph Report - /workspace/spring-ai-alibaba-admin/spring-ai-alibaba-admin-server-openapi  (2026-05-27)

## Corpus Check
- Corpus is ~1,621 words - fits in a single context window. You may not need a graph.

## Summary
- 41 nodes · 85 edges · 8 communities (7 shown, 1 thin omitted)
- Extraction: 100% EXTRACTED · 0% INFERRED · 0% AMBIGUOUS
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_API Key Auth Interceptor|API Key Auth Interceptor]]
- [[_COMMUNITY_Chat Controller Service Dependencies|Chat Controller Service Dependencies]]
- [[_COMMUNITY_Chat Completion Streaming Controller|Chat Completion Streaming Controller]]
- [[_COMMUNITY_Async Workflow Task Controller|Async Workflow Task Controller]]
- [[_COMMUNITY_Task Stop Controller|Task Stop Controller]]
- [[_COMMUNITY_SSE Completion Signal Handler|SSE Completion Signal Handler]]
- [[_COMMUNITY_Reactive Error Handler|Reactive Error Handler]]
- [[_COMMUNITY_Async Results Polling|Async Results Polling]]

## God Nodes (most connected - your core abstractions)
1. `ChatController` - 9 edges
2. `PostMapping` - 5 edges
3. `WorkflowRequest` - 5 edges
4. `RequestContext` - 5 edges
5. `Result` - 5 edges
6. `ApiKeyAuthInterceptor` - 4 edges
7. `AgentRequest` - 4 edges
8. `HttpServletResponse` - 3 edges
9. `ErrorCode` - 3 edges
10. `HttpServletResponse` - 3 edges

## Surprising Connections (you probably didn't know these)
- None detected - all connections are within the same source files.

## Communities (8 total, 1 thin omitted)

### Community 0 - "API Key Auth Interceptor"
Cohesion: 0.33
Nodes (7): ErrorCode, HandlerInterceptor, HttpServletRequest, ApiKeyAuthInterceptor, HttpServletResponse, Object, Override

### Community 1 - "Chat Controller Service Dependencies"
Cohesion: 0.53
Nodes (4): AgentService, ChatController, RedisManager, WorkflowService

### Community 2 - "Chat Completion Streaming Controller"
Cohesion: 0.47
Nodes (4): AgentRequest, HttpServletResponse, Object, WorkflowResponse

### Community 3 - "Async Workflow Task Controller"
Cohesion: 0.50
Nodes (3): PostMapping, TaskRunResponse, WorkflowRequest

### Community 4 - "Task Stop Controller"
Cohesion: 0.50
Nodes (3): Boolean, Result, TaskStopRequest

### Community 5 - "SSE Completion Signal Handler"
Cohesion: 0.50
Nodes (3): RequestContext, SignalType, SseEmitter

### Community 6 - "Reactive Error Handler"
Cohesion: 0.50
Nodes (3): AgentResponse, Mono, Throwable

## Knowledge Gaps
- **5 isolated node(s):** `Object`, `Override`, `Object`, `Throwable`, `Boolean`
  These have ≤1 connection - possible missing edges or undocumented components.
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `ErrorCode` connect `API Key Auth Interceptor` to `Chat Controller Service Dependencies`?**
  _High betweenness centrality (0.148) - this node is a cross-community bridge._
- **Why does `RequestContext` connect `SSE Completion Signal Handler` to `API Key Auth Interceptor`, `Chat Controller Service Dependencies`, `Chat Completion Streaming Controller`, `Reactive Error Handler`?**
  _High betweenness centrality (0.119) - this node is a cross-community bridge._
- **Why does `ChatController` connect `Chat Controller Service Dependencies` to `Chat Completion Streaming Controller`, `Async Workflow Task Controller`, `Task Stop Controller`, `SSE Completion Signal Handler`, `Reactive Error Handler`, `Async Results Polling`?**
  _High betweenness centrality (0.110) - this node is a cross-community bridge._
- **What connects `Object`, `Override`, `Object` to the rest of the system?**
  _5 weakly-connected nodes found - possible documentation gaps or missing edges._