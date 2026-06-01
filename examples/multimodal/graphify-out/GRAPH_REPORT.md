# Graph Report - /workspace/examples/multimodal  (2026-06-01)

## Corpus Check
- Corpus is ~15,734 words - fits in a single context window. You may not need a graph.

## Summary
- 163 nodes · 242 edges · 17 communities (12 shown, 5 thin omitted)
- Extraction: 90% EXTRACTED · 10% INFERRED · 0% AMBIGUOUS · INFERRED: 23 edges (avg confidence: 0.74)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_REST API Controllers & Endpoints|REST API Controllers & Endpoints]]
- [[_COMMUNITY_TTS Audio Service & Format Conversion|TTS Audio Service & Format Conversion]]
- [[_COMMUNITY_DashScope Image Generation Configuration|DashScope Image Generation Configuration]]
- [[_COMMUNITY_Generate Image Tool & Vision Agent Bean|Generate Image Tool & Vision Agent Bean]]
- [[_COMMUNITY_Image Understanding Service Methods|Image Understanding Service Methods]]
- [[_COMMUNITY_Creative Agent Media & Framework|Creative Agent Media & Framework]]
- [[_COMMUNITY_Audio Synthesis Implementation|Audio Synthesis Implementation]]
- [[_COMMUNITY_API Error Handling & Exceptions|API Error Handling & Exceptions]]
- [[_COMMUNITY_Project Setup & Known Limitations|Project Setup & Known Limitations]]
- [[_COMMUNITY_Creative Agent Bean Configuration|Creative Agent Bean Configuration]]
- [[_COMMUNITY_Vision Model Settings (qwen-vl)|Vision Model Settings (qwen-vl)]]
- [[_COMMUNITY_Creative Service Agent Calls|Creative Service Agent Calls]]
- [[_COMMUNITY_Spring Boot Application Entry|Spring Boot Application Entry]]
- [[_COMMUNITY_File Upload Size Limits|File Upload Size Limits]]
- [[_COMMUNITY_Audio Configuration Placeholder|Audio Configuration Placeholder]]
- [[_COMMUNITY_Spring Boot Starter|Spring Boot Starter]]
- [[_COMMUNITY_Image Service Package Reference|Image Service Package Reference]]

## God Nodes (most connected - your core abstractions)
1. `MultimodalController` - 9 edges
2. `Spring AI Alibaba Multimodal Demo` - 9 edges
3. `DashScope AI Platform` - 8 edges
4. `ResponseEntity` - 7 edges
5. `PostMapping` - 7 edges
6. `qwen-vl-plus Vision Model` - 7 edges
7. `Map` - 6 edges
8. `String` - 6 edges
9. `ImageService` - 6 edges
10. `ReactAgent` - 6 edges

## Surprising Connections (you probably didn't know these)
- `MultimodalController (REST Controller)` --implements--> `Spring AI Alibaba Multimodal Demo`  [INFERRED]
  examples/multimodal/src/main/java/com/alibaba/cloud/ai/examples/multimodal/MultimodalController.java → examples/multimodal/README.md
- `creative.CreativeService` --implements--> `ReactAgent`  [INFERRED]
  examples/multimodal/src/main/java/com/alibaba/cloud/ai/examples/multimodal/creative/CreativeService.java → examples/multimodal/README.md
- `audio.AudioService` --implements--> `AudioService`  [EXTRACTED]
  examples/multimodal/src/main/java/com/alibaba/cloud/ai/examples/multimodal/audio/AudioService.java → examples/multimodal/README.md
- `MultimodalController (REST Controller)` --implements--> `POST /api/audio/tts`  [INFERRED]
  examples/multimodal/src/main/java/com/alibaba/cloud/ai/examples/multimodal/MultimodalController.java → examples/multimodal/README.md
- `ClassPathResource` --references--> `sample.png Test Image Resource`  [EXTRACTED]
  examples/multimodal/README.md → examples/multimodal/src/main/resources/images/sample.png

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **Scenario 1: Image Understanding from URL via ChatModel** — readme_chatmodel, readme_usermessage, readme_usermessage_media, readme_media_class, readme_prompt, readme_chatresponse, readme_qwen_vl_plus [EXTRACTED 1.00]
- **Scenario 2: Image Understanding from Local Resource** — readme_chatmodel, readme_usermessage, readme_usermessage_media, readme_media_class, readme_classpathresource, readme_filesystemresource, readme_sample_png [EXTRACTED 1.00]
- **Scenario 3: ReactAgent with Multimodal Input** — readme_reactagent, readme_usermessage, readme_usermessage_media, readme_media_class, readme_assistantmessage, readme_qwen_vl_plus [EXTRACTED 1.00]
- **Scenario 4: Image Generation via GenerateImageTool** — readme_reactagent, readme_generateimagetool, readme_imagemodel, readme_wanx, readme_toolmultimodalresult, readme_multimodaltoolcallresultconverter, readme_outputformat_url, readme_outputformat_base64 [EXTRACTED 1.00]
- **Scenario 5: TTS via DashScopeAudioSpeechModel (Direct API)** — readme_dashscopeaudiospeechmodel, readme_audioservice, readme_cosyvoice, readme_api_audio_tts, readme_outputformat_url, readme_outputformat_base64 [EXTRACTED 1.00]
- **DashScope Supported Vision Model Family** — readme_qwen_vl_plus, readme_qwen_vl_max, readme_qwen2_vl_plus, readme_qwen3_vl_plus [EXTRACTED 1.00]
- **DashScope Model Triad (Vision / Image / TTS)** — readme_qwen_vl_plus, readme_wanx, readme_cosyvoice [EXTRACTED 1.00]
- **Output Format Options: URL vs base64** — readme_outputformat_url, readme_outputformat_base64, readme_generateimagetool, readme_audioservice [EXTRACTED 1.00]
- **Application Configuration Properties Group** — application_multimodal_example, application_max_file_size, application_max_request_size, application_image_model_dashscope, application_image_enabled, application_api_key_config, application_chat_model_config, application_multi_model_flag, application_dashscope_vision_model_env, application_ai_dashscope_api_key_env [EXTRACTED 1.00]
- **Multimodal Tool Result Architecture** — readme_toolmultimodalresult, readme_multimodaltoolcallresultconverter, readme_toolcallresultconverter, readme_imageresponse, readme_media_class [EXTRACTED 1.00]
- **Java Package Structure (com.alibaba.cloud.ai.examples.multimodal)** — code_multimodalapplication, code_multimodalcontroller, code_multimodalexceptionhandler, code_generateimagetool, code_imageconfig, code_imageservice, code_creativeconfig, code_creativeservice, code_audioservice, code_audioconfig [EXTRACTED 1.00]
- **Maven Dependencies for Multimodal Demo** — pom_spring_boot_3_5_7, pom_spring_ai_bom, pom_spring_ai_alibaba_bom, pom_spring_ai_alibaba_extensions_bom, pom_starter_dashscope, pom_dashscope_lib, pom_agent_framework, pom_spring_boot_starter, pom_spring_boot_starter_web, pom_java_17 [EXTRACTED 1.00]
- **Current Known Limitations** — readme_checkpoint_limitation, readme_studio_limitation [EXTRACTED 1.00]

## Communities (17 total, 5 thin omitted)

### Community 0 - "REST API Controllers & Endpoints"
Cohesion: 0.18
Nodes (15): AudioService, CreativeRequest, CreativeService, GetMapping, ImageResourceRequest, ImageService, ImageUrlRequest, Map (+7 more)

### Community 1 - "TTS Audio Service & Format Conversion"
Cohesion: 0.14
Nodes (16): audio.AudioConfig, audio.AudioService, MultimodalController (REST Controller), MultimodalExceptionHandler (Error Handler), spring-ai-alibaba-dashscope Dependency, Spring AI Alibaba Extensions BOM 1.1.2.2, spring-boot-starter-web Dependency, POST /api/audio/tts (+8 more)

### Community 2 - "DashScope Image Generation Configuration"
Cohesion: 0.15
Nodes (15): AI_DASHSCOPE_API_KEY Environment Variable, spring.ai.dashscope.api-key Config, spring.ai.dashscope.image.enabled: true, spring.ai.model.image: dashscope, image.GenerateImageTool, image.ImageConfig, Spring AI Alibaba BOM 1.1.2.2, spring-ai-alibaba-starter-dashscope Dependency (+7 more)

### Community 3 - "Generate Image Tool & Vision Agent Bean"
Cohesion: 0.19
Nodes (10): GenerateImageTool, String, ToolMultimodalResult, ImageConfig, Bean, ChatModel, ReactAgent, ImageModel (+2 more)

### Community 4 - "Image Understanding Service Methods"
Cohesion: 0.23
Nodes (8): ImageService, AssistantMessage, ChatModel, ReactAgent, String, MimeType, Resource, UserMessage

### Community 5 - "Creative Agent Media & Framework"
Cohesion: 0.15
Nodes (14): creative.CreativeConfig, creative.CreativeService, spring-ai-alibaba-agent-framework Dependency, AssistantMessage, ChatModel (Spring AI), ChatResponse, ClassPathResource, FileSystemResource (+6 more)

### Community 6 - "Audio Synthesis Implementation"
Cohesion: 0.29
Nodes (7): AudioService, String, ToolMultimodalResult, DashScopeAudioSpeechModel, Flux, OutputFormat, TextToSpeechResponse

### Community 7 - "API Error Handling & Exceptions"
Cohesion: 0.36
Nodes (8): ExceptionHandler, GraphRunnerException, IllegalArgumentException, MaxUploadSizeExceededException, Map, ResponseEntity, String, MultimodalExceptionHandler

### Community 8 - "Project Setup & Known Limitations"
Cohesion: 0.18
Nodes (11): multimodal-example Spring Application, MultimodalApplication (Main Class), Java 17 (Compile Target), Spring AI BOM 1.1.2, Spring Boot 3.5.7 (Parent), Checkpoint/Resume Limitation, JDK 17+ Prerequisite, Maven Wrapper (mvnw) (+3 more)

### Community 9 - "Creative Agent Bean Configuration"
Cohesion: 0.48
Nodes (5): CreativeConfig, Bean, ChatModel, ReactAgent, GenerateImageTool

### Community 10 - "Vision Model Settings (qwen-vl)"
Cohesion: 0.33
Nodes (7): chat.options.model: qwen-vl-plus (via DASHSCOPE_VISION_MODEL env), DASHSCOPE_VISION_MODEL Environment Variable, multi-model: true Flag, qwen2-vl-plus Vision Model, qwen3-vl-plus Vision Model, qwen-vl-max Vision Model, qwen-vl-plus Vision Model

### Community 11 - "Creative Service Agent Calls"
Cohesion: 0.40
Nodes (3): CreativeService, AssistantMessage, String

## Knowledge Gaps
- **45 isolated node(s):** `String`, `ImageResourceRequest`, `CreativeRequest`, `Object`, `TtsRequest` (+40 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **5 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `DashScope AI Platform` connect `DashScope Image Generation Configuration` to `Project Setup & Known Limitations`, `Vision Model Settings (qwen-vl)`?**
  _High betweenness centrality (0.068) - this node is a cross-community bridge._
- **Why does `GraphRunnerException` connect `API Error Handling & Exceptions` to `REST API Controllers & Endpoints`, `Creative Service Agent Calls`, `Image Understanding Service Methods`?**
  _High betweenness centrality (0.059) - this node is a cross-community bridge._
- **Why does `Spring AI Alibaba Multimodal Demo` connect `Project Setup & Known Limitations` to `TTS Audio Service & Format Conversion`, `DashScope Image Generation Configuration`?**
  _High betweenness centrality (0.051) - this node is a cross-community bridge._
- **What connects `String`, `ImageResourceRequest`, `CreativeRequest` to the rest of the system?**
  _45 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `TTS Audio Service & Format Conversion` be split into smaller, more focused modules?**
  _Cohesion score 0.14166666666666666 - nodes in this community are weakly interconnected._