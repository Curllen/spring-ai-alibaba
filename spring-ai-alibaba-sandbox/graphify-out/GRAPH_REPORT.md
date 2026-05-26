# Graph Report - /workspace/spring-ai-alibaba-sandbox  (2026-05-26)

## Corpus Check
- Corpus is ~13,637 words - fits in a single context window. You may not need a graph.

## Summary
- 836 nodes · 1517 edges · 47 communities (44 shown, 3 thin omitted)
- Extraction: 88% EXTRACTED · 12% INFERRED · 0% AMBIGUOUS · INFERRED: 183 edges (avg confidence: 0.8)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Build|Build]]
- [[_COMMUNITY_Browser Toolkit Init|Browser Toolkit Init]]
- [[_COMMUNITY_Browser Saa Adapter|Browser Saa Adapter]]
- [[_COMMUNITY_Edit Response Saa|Edit Response Saa]]
- [[_COMMUNITY_Python Response Run|Python Response Run]]
- [[_COMMUNITY_Shell Response Run|Shell Response Run]]
- [[_COMMUNITY_Navigate Response Saa|Navigate Response Saa]]
- [[_COMMUNITY_Tab Response Select|Tab Response Select]]
- [[_COMMUNITY_Allowed Directories Response|Allowed Directories Response]]
- [[_COMMUNITY_Directory Create Response|Directory Create Response]]
- [[_COMMUNITY_Info Response Saa|Info Response Saa]]
- [[_COMMUNITY_Move Response Saa|Move Response Saa]]
- [[_COMMUNITY_Read Response Saa|Read Response Saa]]
- [[_COMMUNITY_Response Write Saa|Response Write Saa]]
- [[_COMMUNITY_Tree Directory Response|Tree Directory Response]]
- [[_COMMUNITY_Directory Response Saa|Directory Response Saa]]
- [[_COMMUNITY_Click Response Saa|Click Response Saa]]
- [[_COMMUNITY_Resize Response Saa|Resize Response Saa]]
- [[_COMMUNITY_Response Search Saa|Response Search Saa]]
- [[_COMMUNITY_Read Response Saa (2)|Read Response Saa (2)]]
- [[_COMMUNITY_Back Navigate Response|Back Navigate Response]]
- [[_COMMUNITY_Close Response Saa|Close Response Saa]]
- [[_COMMUNITY_Console Response Saa|Console Response Saa]]
- [[_COMMUNITY_Upload Response Saa|Upload Response Saa]]
- [[_COMMUNITY_Forward Navigate Response|Forward Navigate Response]]
- [[_COMMUNITY_Hover Response Saa|Hover Response Saa]]
- [[_COMMUNITY_Option Response Select|Option Response Select]]
- [[_COMMUNITY_Snapshot Response Saa|Snapshot Response Saa]]
- [[_COMMUNITY_Tab Response Saa|Tab Response Saa]]
- [[_COMMUNITY_Drag Response Saa|Drag Response Saa]]
- [[_COMMUNITY_Press Response Saa|Press Response Saa]]
- [[_COMMUNITY_Network Requests Response|Network Requests Response]]
- [[_COMMUNITY_Pdf Response Save|Pdf Response Save]]
- [[_COMMUNITY_Screenshot Response Saa|Screenshot Response Saa]]
- [[_COMMUNITY_Tab Response Saa (2)|Tab Response Saa (2)]]
- [[_COMMUNITY_Tab Response Saa (3)|Tab Response Saa (3)]]
- [[_COMMUNITY_Response Saa Browser|Response Saa Browser]]
- [[_COMMUNITY_Response Saa Browser (2)|Response Saa Browser (2)]]
- [[_COMMUNITY_Dialog Response Handle|Dialog Response Handle]]
- [[_COMMUNITY_Runtime Metadata|Runtime Metadata]]
- [[_COMMUNITY_Mcptool Saa Response|Mcptool Saa Response]]
- [[_COMMUNITY_Sandbox Base Aware|Sandbox Base Aware]]
- [[_COMMUNITY_Sandbox Aware|Sandbox Aware]]
- [[_COMMUNITY_Miscellaneous Components|Miscellaneous Components]]
- [[_COMMUNITY_Miscellaneous Components (2)|Miscellaneous Components (2)]]
- [[_COMMUNITY_Miscellaneous Components (3)|Miscellaneous Components (3)]]
- [[_COMMUNITY_Miscellaneous Components (4)|Miscellaneous Components (4)]]

## God Nodes (most connected - your core abstractions)
1. `ToolCallback` - 42 edges
2. `ToolkitInit` - 41 edges
3. `ToolMetadata` - 41 edges
4. `Sandbox` - 38 edges
5. `BaseSandboxAwareTool abstract class - generic adapter that delegates sandbox management to an underlying SandboxTool` - 38 edges
6. `RuntimeFunctionToolCallback - Spring AI ToolCallback wrapper that marshals JSON input, delegates to a SandboxAwareTool, and returns converted output` - 23 edges
7. `ToolkitInit - static factory that instantiates all sandbox tools, wraps them as ToolCallbacks, and handles MCP tool configuration` - 19 edges
8. `RuntimeFunctionToolCallback` - 10 edges
9. `I` - 10 edges
10. `O` - 10 edges

## Surprising Connections (you probably didn't know these)
- `SaaMCPTool` --semantically_similar_to--> `SaaBrowserHoverer`  [AMBIGUOUS] [semantically similar]
  src/main/java/com/alibaba/cloud/ai/sandbox/tools/mcp/SaaMCPTool.java → src/main/java/com/alibaba/cloud/ai/sandbox/tools/browser/SaaBrowserHoverer.java
- `SaaBrowserWindowResizer` --semantically_similar_to--> `SaaFsAllowedDirectoriesLister`  [AMBIGUOUS] [semantically similar]
  src/main/java/com/alibaba/cloud/ai/sandbox/tools/browser/SaaBrowserWindowResizer.java → src/main/java/com/alibaba/cloud/ai/sandbox/tools/fs/SaaFsAllowedDirectoriesLister.java
- `SaaMCPTool` --semantically_similar_to--> `SaaFsFileReader`  [AMBIGUOUS] [semantically similar]
  src/main/java/com/alibaba/cloud/ai/sandbox/tools/mcp/SaaMCPTool.java → src/main/java/com/alibaba/cloud/ai/sandbox/tools/fs/SaaFsFileReader.java
- `SaaBaseShellRunner - adapter wrapping agentscope RunShellCommandTool for shell command execution in sandbox` --semantically_similar_to--> `SaaBasePythonRunner - adapter wrapping agentscope RunPythonTool for Python code execution in sandbox`  [INFERRED] [semantically similar]
  src/main/java/com/alibaba/cloud/ai/sandbox/tools/base/SaaBaseShellRunner.java → src/main/java/com/alibaba/cloud/ai/sandbox/tools/base/SaaBasePythonRunner.java
- `SaaBrowserTabLister - adapter wrapping agentscope TabListTool to list browser tabs` --semantically_similar_to--> `SaaBrowserTabCreator - adapter wrapping agentscope TabNewTool to create new browser tabs with a URL`  [INFERRED] [semantically similar]
  src/main/java/com/alibaba/cloud/ai/sandbox/tools/browser/SaaBrowserTabLister.java → src/main/java/com/alibaba/cloud/ai/sandbox/tools/browser/SaaBrowserTabCreator.java

## Hyperedges (group relationships)
- **Browser Tool Adapter Pattern** — SaaBrowserTabLister_SaaBrowserTabLister, SaaBrowserDragger_SaaBrowserDragger, SaaBrowserCloser_SaaBrowserCloser, SaaBrowserWaiter_SaaBrowserWaiter, SaaBrowserTabCreator_SaaBrowserTabCreator, SaaBrowserClicker_SaaBrowserClicker, SaaBrowserNavigator_SaaBrowserNavigator, SaaBrowserTabSelector_SaaBrowserTabSelector, SaaBrowserDialogHandler_SaaBrowserDialogHandler, SaaBrowserBackNavigator_SaaBrowserBackNavigator, SaaBrowserSnapshotTaker_SaaBrowserSnapshotTaker, SaaBrowserKeyPresser_SaaBrowserKeyPresser, SaaBrowserConsoleMessagesRetriever_SaaBrowserConsoleMessagesRetriever, SaaBrowserTabCloser_SaaBrowserTabCloser, SaaBrowserOptionSelector_SaaBrowserOptionSelector, SaaBrowserTyper_SaaBrowserTyper [INFERRED 0.90]
- **Core Sandbox Tool Adapter Framework** — SandboxAwareTool_SandboxAwareTool, BaseSandboxAwareTool_BaseSandboxAwareTool, RuntimeFunctionToolCallback_RuntimeFunctionToolCallback, ToolkitInit_ToolkitInit [EXTRACTED 1.00]
- **Tab Lifecycle Management Cluster** — SaaBrowserTabLister_SaaBrowserTabLister, SaaBrowserTabCreator_SaaBrowserTabCreator, SaaBrowserTabSelector_SaaBrowserTabSelector, SaaBrowserTabCloser_SaaBrowserTabCloser [INFERRED 0.85]
- **Browser Tool Wrapper Group** — SaaBrowserHoverer_SaaBrowserHoverer, SaaBrowserScreenshotTaker_SaaBrowserScreenshotTaker, SaaBrowserWindowResizer_SaaBrowserWindowResizer, SaaBrowserFileUploader_SaaBrowserFileUploader, SaaBrowserForwardNavigator_SaaBrowserForwardNavigator, SaaBrowserPdfSaver_SaaBrowserPdfSaver, SaaBrowserNetworkRequestsRetriever_SaaBrowserNetworkRequestsRetriever [INFERRED 0.85]
- **Filesystem Tool Wrapper Group** — SaaFsFileSearcher_SaaFsFileSearcher, SaaFsDirectoryCreator_SaaFsDirectoryCreator, SaaFsFileInfoRetriever_SaaFsFileInfoRetriever, SaaFsMultiFileReader_SaaFsMultiFileReader, SaaFsDirectoryLister_SaaFsDirectoryLister, SaaFsFileWriter_SaaFsFileWriter, SaaFsFileReader_SaaFsFileReader, SaaFsFileEditor_SaaFsFileEditor, SaaFsTreeBuilder_SaaFsTreeBuilder, SaaFsAllowedDirectoriesLister_SaaFsAllowedDirectoriesLister, SaaFsFileMover_SaaFsFileMover [INFERRED 0.85]
- **Sandbox Tool Adapter Pattern** — SaaBrowserHoverer_SaaBrowserHoverer, SaaFsFileReader_SaaFsFileReader, SaaMCPTool_SaaMCPTool, BaseSandboxAwareTool_BaseSandboxAwareTool, RuntimeFunctionToolCallback_RuntimeFunctionToolCallback [INFERRED 0.90]

## Communities (47 total, 3 thin omitted)

### Community 0 - "Build"
Cohesion: 0.11
Nodes (10): AfterAll, BeforeAll, Builder, I, String, O, AgentToolTest, Builder (+2 more)

### Community 1 - "Browser Toolkit Init"
Cohesion: 0.13
Nodes (11): List, Map, MCPTool, Object, Sandbox, SandboxService, String, ToolCallback (+3 more)

### Community 2 - "Browser Saa Adapter"
Cohesion: 0.11
Nodes (44): BaseSandboxAwareTool abstract class - generic adapter that delegates sandbox management to an underlying SandboxTool, RuntimeFunctionToolCallback - Spring AI ToolCallback wrapper that marshals JSON input, delegates to a SandboxAwareTool, and returns converted output, SaaBasePythonRunner - adapter wrapping agentscope RunPythonTool for Python code execution in sandbox, SaaBaseShellRunner - adapter wrapping agentscope RunShellCommandTool for shell command execution in sandbox, SaaBrowserBackNavigator - adapter wrapping agentscope NavigateBackTool for browser history back navigation, SaaBrowserClicker - adapter wrapping agentscope ClickTool to click elements by description and snapshot reference, SaaBrowserCloser - adapter wrapping agentscope CloseTool to close the browser instance, SaaBrowserConsoleMessagesRetriever - adapter wrapping agentscope ConsoleMessagesTool to retrieve browser console messages (+36 more)

### Community 3 - "Edit Response Saa"
Cohesion: 0.15
Nodes (17): EditFileToolRequest, EditFileToolResponse, EditFileToolRequest(), EditFileToolResponse(), message(), Response(), result(), SaaFsFileEditor (+9 more)

### Community 4 - "Python Response Run"
Cohesion: 0.16
Nodes (15): message(), Response(), result(), RunPythonToolRequest(), RunPythonToolResponse(), SaaBasePythonRunner, JsonProperty, JsonPropertyDescription (+7 more)

### Community 5 - "Shell Response Run"
Cohesion: 0.16
Nodes (15): message(), Response(), result(), RunShellCommandToolRequest(), RunShellCommandToolResponse(), SaaBaseShellRunner, JsonProperty, JsonPropertyDescription (+7 more)

### Community 6 - "Navigate Response Saa"
Cohesion: 0.16
Nodes (15): message(), NavigateToolRequest(), NavigateToolResponse(), Response(), result(), SaaBrowserNavigator, JsonProperty, JsonPropertyDescription (+7 more)

### Community 7 - "Tab Response Select"
Cohesion: 0.14
Nodes (15): message(), Response(), result(), SaaBrowserTabSelector, TabSelectToolRequest(), TabSelectToolResponse(), Integer, JsonProperty (+7 more)

### Community 8 - "Allowed Directories Response"
Cohesion: 0.16
Nodes (14): ListAllowedDirectoriesToolResponse(), message(), Response(), result(), SaaFsAllowedDirectoriesLister, ListAllowedDirectoriesToolRequest, ListAllowedDirectoriesToolResponse, JsonProperty (+6 more)

### Community 9 - "Directory Create Response"
Cohesion: 0.16
Nodes (15): CreateDirectoryToolRequest, CreateDirectoryToolResponse, CreateDirectoryToolRequest(), CreateDirectoryToolResponse(), message(), Response(), result(), SaaFsDirectoryCreator (+7 more)

### Community 10 - "Info Response Saa"
Cohesion: 0.16
Nodes (15): GetFileInfoToolRequest(), GetFileInfoToolResponse(), message(), Response(), result(), SaaFsFileInfoRetriever, GetFileInfoToolRequest, GetFileInfoToolResponse (+7 more)

### Community 11 - "Move Response Saa"
Cohesion: 0.16
Nodes (15): message(), MoveFileToolRequest(), MoveFileToolResponse(), Response(), result(), SaaFsFileMover, JsonProperty, JsonPropertyDescription (+7 more)

### Community 12 - "Read Response Saa"
Cohesion: 0.16
Nodes (15): message(), ReadFileToolRequest(), ReadFileToolResponse(), Response(), result(), SaaFsFileReader, JsonProperty, JsonPropertyDescription (+7 more)

### Community 13 - "Response Write Saa"
Cohesion: 0.16
Nodes (15): message(), Response(), result(), SaaFsFileWriter, WriteFileToolRequest(), WriteFileToolResponse(), JsonProperty, JsonPropertyDescription (+7 more)

### Community 14 - "Tree Directory Response"
Cohesion: 0.16
Nodes (15): DirectoryTreeToolRequest, DirectoryTreeToolResponse, DirectoryTreeToolRequest(), DirectoryTreeToolResponse(), message(), Response(), result(), SaaFsTreeBuilder (+7 more)

### Community 15 - "Directory Response Saa"
Cohesion: 0.16
Nodes (15): ListDirectoryToolRequest(), ListDirectoryToolResponse(), message(), Response(), result(), SaaFsDirectoryLister, ListDirectoryToolRequest, ListDirectoryToolResponse (+7 more)

### Community 16 - "Click Response Saa"
Cohesion: 0.16
Nodes (15): ClickToolRequest(), ClickToolResponse(), message(), Response(), result(), SaaBrowserClicker, ClickToolRequest, ClickToolResponse (+7 more)

### Community 17 - "Resize Response Saa"
Cohesion: 0.14
Nodes (15): message(), ResizeToolRequest(), ResizeToolResponse(), Response(), result(), SaaBrowserWindowResizer, Double, JsonProperty (+7 more)

### Community 18 - "Response Search Saa"
Cohesion: 0.16
Nodes (15): message(), Response(), result(), SaaFsFileSearcher, SearchFilesToolRequest(), SearchFilesToolResponse(), JsonProperty, JsonPropertyDescription (+7 more)

### Community 19 - "Read Response Saa (2)"
Cohesion: 0.16
Nodes (15): message(), ReadMultipleFilesToolRequest(), ReadMultipleFilesToolResponse(), Response(), result(), SaaFsMultiFileReader, JsonProperty, JsonPropertyDescription (+7 more)

### Community 20 - "Back Navigate Response"
Cohesion: 0.15
Nodes (13): message(), NavigateBackToolResponse(), Response(), result(), SaaBrowserBackNavigator, JsonProperty, Override, Response (+5 more)

### Community 21 - "Close Response Saa"
Cohesion: 0.15
Nodes (13): CloseToolResponse(), message(), Response(), result(), SaaBrowserCloser, CloseToolRequest, CloseToolResponse, JsonProperty (+5 more)

### Community 22 - "Console Response Saa"
Cohesion: 0.15
Nodes (13): ConsoleMessagesToolResponse(), message(), Response(), result(), SaaBrowserConsoleMessagesRetriever, ConsoleMessagesToolRequest, ConsoleMessagesToolResponse, JsonProperty (+5 more)

### Community 23 - "Upload Response Saa"
Cohesion: 0.16
Nodes (14): FileUploadToolRequest(), FileUploadToolResponse(), message(), Response(), result(), SaaBrowserFileUploader, FileUploadToolRequest, FileUploadToolResponse (+6 more)

### Community 24 - "Forward Navigate Response"
Cohesion: 0.15
Nodes (13): message(), NavigateForwardToolResponse(), Response(), result(), SaaBrowserForwardNavigator, JsonProperty, Override, Response (+5 more)

### Community 25 - "Hover Response Saa"
Cohesion: 0.16
Nodes (14): HoverToolRequest(), HoverToolResponse(), message(), Response(), result(), SaaBrowserHoverer, HoverToolRequest, HoverToolResponse (+6 more)

### Community 26 - "Option Response Select"
Cohesion: 0.16
Nodes (14): message(), Response(), result(), SaaBrowserOptionSelector, SelectOptionToolRequest(), SelectOptionToolResponse(), JsonProperty, Override (+6 more)

### Community 27 - "Snapshot Response Saa"
Cohesion: 0.15
Nodes (13): message(), Response(), result(), SaaBrowserSnapshotTaker, SnapshotToolResponse(), JsonProperty, Override, Response (+5 more)

### Community 28 - "Tab Response Saa"
Cohesion: 0.15
Nodes (13): message(), Response(), result(), SaaBrowserTabLister, TabListToolResponse(), JsonProperty, Override, Response (+5 more)

### Community 29 - "Drag Response Saa"
Cohesion: 0.16
Nodes (14): DragToolRequest(), DragToolResponse(), message(), Response(), result(), SaaBrowserDragger, DragToolRequest, DragToolResponse (+6 more)

### Community 30 - "Press Response Saa"
Cohesion: 0.16
Nodes (14): message(), PressKeyToolRequest(), PressKeyToolResponse(), Response(), result(), SaaBrowserKeyPresser, JsonProperty, Override (+6 more)

### Community 31 - "Network Requests Response"
Cohesion: 0.15
Nodes (13): message(), NetworkRequestsToolResponse(), Response(), result(), SaaBrowserNetworkRequestsRetriever, JsonProperty, Override, Response (+5 more)

### Community 32 - "Pdf Response Save"
Cohesion: 0.17
Nodes (13): message(), PdfSaveToolResponse(), Response(), result(), SaaBrowserPdfSaver, JsonProperty, Override, Response (+5 more)

### Community 33 - "Screenshot Response Saa"
Cohesion: 0.17
Nodes (13): message(), Response(), result(), SaaBrowserScreenshotTaker, TakeScreenshotToolResponse(), JsonProperty, Override, Response (+5 more)

### Community 34 - "Tab Response Saa (2)"
Cohesion: 0.17
Nodes (13): message(), Response(), result(), SaaBrowserTabCloser, TabCloseToolResponse(), JsonProperty, Override, Response (+5 more)

### Community 35 - "Tab Response Saa (3)"
Cohesion: 0.17
Nodes (13): message(), Response(), result(), SaaBrowserTabCreator, TabNewToolResponse(), JsonProperty, Override, Response (+5 more)

### Community 36 - "Response Saa Browser"
Cohesion: 0.17
Nodes (13): message(), Response(), result(), SaaBrowserTyper, TypeToolResponse(), JsonProperty, Override, Response (+5 more)

### Community 37 - "Response Saa Browser (2)"
Cohesion: 0.17
Nodes (13): message(), Response(), result(), SaaBrowserWaiter, WaitForToolResponse(), JsonProperty, Override, Response (+5 more)

### Community 38 - "Dialog Response Handle"
Cohesion: 0.17
Nodes (13): HandleDialogToolResponse(), message(), Response(), result(), SaaBrowserDialogHandler, HandleDialogToolRequest, HandleDialogToolResponse, JsonProperty (+5 more)

### Community 39 - "Runtime Metadata"
Cohesion: 0.27
Nodes (9): Override, ToolContext, NotNull, ParameterizedTypeReference, RuntimeFunctionToolCallback, ToolCallResultConverter, ToolDefinition, ToolMetadata (+1 more)

### Community 40 - "Mcptool Saa Response"
Cohesion: 0.23
Nodes (11): Map, MCPTool, Object, Override, RuntimeFunctionToolCallback, SandboxService, String, ToolContext (+3 more)

### Community 41 - "Sandbox Base Aware"
Cohesion: 0.29
Nodes (5): Class, Override, Sandbox, BaseSandboxAwareTool, T

### Community 42 - "Sandbox Aware"
Cohesion: 0.38
Nodes (3): Class, Sandbox, SandboxAwareTool

### Community 43 - "Miscellaneous Components"
Cohesion: 0.40
Nodes (5): AgentToolTest, DashScopeChatModel, ReactAgent, SandboxService, ToolkitInit

## Ambiguous Edges - Review These
- `SaaBrowserHoverer` → `SaaMCPTool`  [AMBIGUOUS]
  src/main/java/com/alibaba/cloud/ai/sandbox/tools/ · relation: semantically_similar_to
- `SaaBrowserWindowResizer` → `SaaFsAllowedDirectoriesLister`  [AMBIGUOUS]
  src/main/java/com/alibaba/cloud/ai/sandbox/tools/ · relation: semantically_similar_to
- `SaaFsFileReader` → `SaaMCPTool`  [AMBIGUOUS]
  src/main/java/com/alibaba/cloud/ai/sandbox/tools/ · relation: semantically_similar_to

## Knowledge Gaps
- **160 isolated node(s):** `T`, `Class`, `Class`, `Builder`, `MCPToolResponse` (+155 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **3 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **What is the exact relationship between `SaaBrowserHoverer` and `SaaMCPTool`?**
  _Edge tagged AMBIGUOUS (relation: semantically_similar_to) - confidence is low._
- **What is the exact relationship between `SaaBrowserWindowResizer` and `SaaFsAllowedDirectoriesLister`?**
  _Edge tagged AMBIGUOUS (relation: semantically_similar_to) - confidence is low._
- **What is the exact relationship between `SaaFsFileReader` and `SaaMCPTool`?**
  _Edge tagged AMBIGUOUS (relation: semantically_similar_to) - confidence is low._
- **Why does `ToolMetadata` connect `Runtime Metadata` to `Build`, `Edit Response Saa`, `Python Response Run`, `Shell Response Run`, `Navigate Response Saa`, `Tab Response Select`, `Allowed Directories Response`, `Directory Create Response`, `Info Response Saa`, `Move Response Saa`, `Read Response Saa`, `Response Write Saa`, `Tree Directory Response`, `Directory Response Saa`, `Click Response Saa`, `Resize Response Saa`, `Response Search Saa`, `Read Response Saa (2)`, `Back Navigate Response`, `Close Response Saa`, `Console Response Saa`, `Upload Response Saa`, `Forward Navigate Response`, `Hover Response Saa`, `Option Response Select`, `Snapshot Response Saa`, `Tab Response Saa`, `Drag Response Saa`, `Press Response Saa`, `Network Requests Response`, `Pdf Response Save`, `Screenshot Response Saa`, `Tab Response Saa (2)`, `Tab Response Saa (3)`, `Response Saa Browser`, `Response Saa Browser (2)`, `Dialog Response Handle`, `Mcptool Saa Response`?**
  _High betweenness centrality (0.606) - this node is a cross-community bridge._
- **Why does `ToolCallback` connect `Browser Toolkit Init` to `Runtime Metadata`?**
  _High betweenness centrality (0.070) - this node is a cross-community bridge._
- **What connects `T`, `Class`, `Class` to the rest of the system?**
  _160 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Build` be split into smaller, more focused modules?**
  _Cohesion score 0.10840824960338445 - nodes in this community are weakly interconnected._