# Graph Report - /workspace/examples/voice-agent  (2026-06-01)

## Corpus Check
- Corpus is ~6,426 words - fits in a single context window. You may not need a graph.

## Summary
- 194 nodes · 332 edges · 12 communities (11 shown, 1 thin omitted)
- Extraction: 93% EXTRACTED · 7% INFERRED · 0% AMBIGUOUS · INFERRED: 23 edges (avg confidence: 0.8)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Audio WebSocket & Realtime Streaming|Audio WebSocket & Realtime Streaming]]
- [[_COMMUNITY_VoiceAgent Stream Service Core|VoiceAgent Stream Service Core]]
- [[_COMMUNITY_ASR-TTS Agent Events & Models|ASR-TTS Agent Events & Models]]
- [[_COMMUNITY_Architecture Comparison & Prerequisites|Architecture Comparison & Prerequisites]]
- [[_COMMUNITY_Text WebSocket Handler & JSON Protocol|Text WebSocket Handler & JSON Protocol]]
- [[_COMMUNITY_Realtime Audio Pipeline Service|Realtime Audio Pipeline Service]]
- [[_COMMUNITY_VoiceAgent Event Type System|VoiceAgent Event Type System]]
- [[_COMMUNITY_WebSocket Route Configuration|WebSocket Route Configuration]]
- [[_COMMUNITY_Realtime ASR Bean Configuration|Realtime ASR Bean Configuration]]
- [[_COMMUNITY_Sandwich Agent Bean Configuration|Sandwich Agent Bean Configuration]]
- [[_COMMUNITY_Sandwich Order Tools|Sandwich Order Tools]]
- [[_COMMUNITY_Spring Boot Application Entry|Spring Boot Application Entry]]

## God Nodes (most connected - your core abstractions)
1. `create()` - 17 edges
2. `VoiceAgentAudioWebSocketHandler` - 13 edges
3. `VoiceAgentStreamService` - 12 edges
4. `VoiceAgentWebSocketHandler` - 12 edges
5. `WebSocket API` - 11 edges
6. `WebSocketSession` - 9 edges
7. `ReactAgent (LLM Agent)` - 9 edges
8. `WebSocketSession` - 8 edges
9. `Voice Agent Example` - 8 edges
10. `RealtimeVoiceAgentStreamService` - 6 edges

## Surprising Connections (you probably didn't know these)
- `voice-agent-example (Spring Application Config)` --references--> `Voice Agent Example`  [EXTRACTED]
  examples/voice-agent/src/main/resources/application.yml → examples/voice-agent/README.md
- `Paraformer Realtime V2` --references--> `streamRecognition (ASR Config)`  [EXTRACTED]
  examples/voice-agent/README.md → examples/voice-agent/src/main/resources/application.yml
- `CosyVoice V3 Flash` --references--> `stream with text input (TTS Config)`  [EXTRACTED]
  examples/voice-agent/README.md → examples/voice-agent/src/main/resources/application.yml
- `voice-agent-example (Spring Application Config)` --references--> `AI_DASHSCOPE_API_KEY`  [EXTRACTED]
  examples/voice-agent/src/main/resources/application.yml → examples/voice-agent/README.md

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **ASR → Agent → TTS Sandwich Pipeline** — stt_component, agent_component, tts_component [EXTRACTED 1.00]
- **DashScope Model Triad for Voice Agent** — paraformer_realtime_v2, qwen_llm, cosyvoice_v3_flash [INFERRED 0.85]
- **Sandwich Shop Order Scenario** — add_to_order_tool, confirm_order_tool, agent_component, sandwich_ingredients [EXTRACTED 1.00]
- **WebSocket Server-Sent Event Protocol** — stt_chunk_event, stt_output_event, agent_chunk_event, tool_call_event, tool_result_event, agent_end_event, tts_chunk_event, error_event [EXTRACTED 1.00]
- **Voice Agent Architecture Comparison: Native S2S vs Combined S2S** — native_s2s, combined_s2s, openai_gpt_realtime, google_gemini_live, elevenlabs_conversational_ai, alicloud_isi, iflytek_spark, baidu_speecht5, microsoft_azure_speech [EXTRACTED 1.00]
- **Realtime Audio WebSocket Flow (Binary In → JSON Events Out)** — ws_audio_endpoint, binary_audio_protocol, end_message, realtime_bidirectional_streaming [EXTRACTED 1.00]
- **Text WebSocket Modes (Full Pipeline + TTS-Only)** — ws_text_endpoint, text_json_protocol, tts_only_mode, agent_component, tts_component [EXTRACTED 1.00]
- **Prerequisites and Configuration** — jdk17_prerequisite, ffmpeg_prerequisite, dashscope_api_key, app_config [EXTRACTED 1.00]
- **DashScope Streaming Configuration** — paraformer_realtime_v2, stream_recognition_config, cosyvoice_v3_flash, stream_tts_config, dashscope_api_key [EXTRACTED 1.00]
- **Web UI Interaction Modes** — web_ui, voice_mode, text_mode, ws_audio_endpoint, ws_text_endpoint [INFERRED 0.85]

## Communities (12 total, 1 thin omitted)

### Community 0 - "Audio WebSocket & Realtime Streaming"
Cohesion: 0.16
Nodes (16): AbstractWebSocketHandler, BinaryMessage, Many, RealtimeVoiceAgentStreamService, ByteBuffer, CloseStatus, Flux, Mono (+8 more)

### Community 1 - "VoiceAgent Stream Service Core"
Cohesion: 0.17
Nodes (13): AudioTranscriptionModel, Resource, Flux, Map, Object, ReactAgent, StreamingInputTextToSpeechModel, String (+5 more)

### Community 2 - "ASR-TTS Agent Events & Models"
Cohesion: 0.11
Nodes (25): add_to_order(item, quantity), agent_chunk Event, ReactAgent (LLM Agent), agent_end Event, confirm_order(order_summary), CosyVoice V3 Flash, DashScope CosyVoice TTS, DashScope Realtime ASR (+17 more)

### Community 3 - "Architecture Comparison & Prerequisites"
Cohesion: 0.09
Nodes (24): 阿里云 智能语音交互 (ISI), voice-agent-example (Spring Application Config), 百度 SpeechT5, Binary Audio Protocol (PCM 16kHz 16-bit mono), Combined S2S (STT + LLM + TTS), DashScope (Alibaba Cloud AI Platform), AI_DASHSCOPE_API_KEY, ElevenLabs Conversational AI 2.0 (+16 more)

### Community 4 - "Text WebSocket Handler & JSON Protocol"
Cohesion: 0.20
Nodes (12): ParsedInput, CloseStatus, Mono, Override, String, TextMessage, VoiceAgentEvent, Void (+4 more)

### Community 5 - "Realtime Audio Pipeline Service"
Cohesion: 0.19
Nodes (13): DashScopeAudioSpeechModel, ByteBuffer, DashScopeAudioTranscriptionModel, Flux, Map, Object, ReactAgent, StreamingInputTextToSpeechModel (+5 more)

### Community 6 - "VoiceAgent Event Type System"
Cohesion: 0.14
Nodes (13): AgentChunkEvent, AgentEndEvent, create(), Map, Object, String, VoiceAgentEvent, SttChunkEvent (+5 more)

### Community 7 - "WebSocket Route Configuration"
Cohesion: 0.28
Nodes (6): Override, WebSocketConfig, VoiceAgentAudioWebSocketHandler, VoiceAgentWebSocketHandler, WebSocketConfigurer, WebSocketHandlerRegistry

### Community 8 - "Realtime ASR Bean Configuration"
Cohesion: 0.39
Nodes (6): ConditionalOnMissingBean, ConditionalOnProperty, Bean, DashScopeAudioTranscriptionModel, String, RealtimeVoiceConfig

### Community 9 - "Sandwich Agent Bean Configuration"
Cohesion: 0.43
Nodes (5): ChatModel, Bean, ReactAgent, SandwichTools, VoiceAgentConfig

### Community 10 - "Sandwich Order Tools"
Cohesion: 0.53
Nodes (3): String, SandwichTools, Tool

## Knowledge Gaps
- **38 isolated node(s):** `String`, `String`, `SandwichTools`, `Object`, `SuppressWarnings` (+33 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `create()` connect `VoiceAgent Event Type System` to `VoiceAgent Stream Service Core`, `Realtime Audio Pipeline Service`?**
  _High betweenness centrality (0.120) - this node is a cross-community bridge._
- **Why does `Many` connect `Audio WebSocket & Realtime Streaming` to `VoiceAgent Stream Service Core`, `Realtime Audio Pipeline Service`?**
  _High betweenness centrality (0.060) - this node is a cross-community bridge._
- **Are the 5 inferred relationships involving `create()` (e.g. with `.runAgentWithStreamingTts()` and `.streamWithAudioRealtime()`) actually correct?**
  _`create()` has 5 INFERRED edges - model-reasoned connections that need verification._
- **What connects `String`, `String`, `SandwichTools` to the rest of the system?**
  _38 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `ASR-TTS Agent Events & Models` be split into smaller, more focused modules?**
  _Cohesion score 0.11333333333333333 - nodes in this community are weakly interconnected._
- **Should `Architecture Comparison & Prerequisites` be split into smaller, more focused modules?**
  _Cohesion score 0.09420289855072464 - nodes in this community are weakly interconnected._
- **Should `VoiceAgent Event Type System` be split into smaller, more focused modules?**
  _Cohesion score 0.14166666666666666 - nodes in this community are weakly interconnected._