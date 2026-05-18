---
title: "Pipecat"
type: "source"
category: "Building_AI_applications"
tags: ["voice-ai", "multimodal", "real-time", "agent-framework", "python"]
created: "2026-05-12"
updated: "2026-05-12"
related_topics: ["topics/building_agent_apps.md"]
---

# Pipecat

- **Type**: Voice & Multimodal AI Agent Framework
- **Slogan**: Real-Time Voice & Multimodal AI Agents

![Pipecat Logo](../media/pipecat_logo.png)

Open-source Python framework for building real-time voice and multimodal conversational agents. Orchestrate audio and video, AI services, different transports, and conversation pipelines effortlessly.

## Details

- **Org**: pipecat-ai
- **License**: BSD-2-Clause
- **GitHub**: [https://github.com/pipecat-ai/pipecat](https://github.com/pipecat-ai/pipecat)
- **Stars**: 12.1k+
- **Documentation**: [https://docs.pipecat.ai](https://docs.pipecat.ai)
- **Website**: [https://pipecat.ai](https://pipecat.ai)
- **PyPI**: [pipecat-ai](https://pypi.org/project/pipecat-ai)

## Key Features

- **Voice-first** — Integrates speech recognition, text-to-speech, and conversation handling
- **Pluggable** — Supports 100+ AI services across STT, LLM, TTS, S2S, Vision, Audio, and more
- **Composable Pipelines** — Build complex behavior from modular components
- **Real-Time** — Ultra-low latency interaction with WebSockets or WebRTC transports
- **Multi-Agent** — Subagents system for distributed multi-agent pipelines

## Available Services

- **Speech-to-Text**: AssemblyAI, AWS, Azure, Cartesia, Deepgram, ElevenLabs, Google, Groq, Mistral, NVIDIA, OpenAI, Whisper, xAI, and 9+ more
- **LLMs**: Anthropic, AWS, Azure, Cerebras, DeepSeek, Gemini, Grok, Groq, Mistral, Ollama, OpenAI, Perplexity, Qwen, Together AI, and 8+ more
- **Text-to-Speech**: AWS, Azure, Cartesia, Deepgram, ElevenLabs, Google, Hume, Kokoro, LMNT, MiniMax, OpenAI, Piper, and 16+ more
- **Speech-to-Speech**: AWS Nova Sonic, Gemini Multimodal Live, Grok Voice Agent, OpenAI Realtime, Ultravox
- **Transport**: Daily (WebRTC), FastAPI Websocket, LiveKit (WebRTC), WebSocket Server, WhatsApp, Local
- **Video**: HeyGen, LemonSlice, Tavus, Simli
- **Memory**: mem0
- **Vision & Image**: fal, Google Imagen, Moondream
- **Audio Processing**: Silero VAD, Krisp Viva, Koala, ai-coustics, RNNoise
- **Analytics**: OpenTelemetry, Sentry

## Pipecat Ecosystem

- [Pipecat Subagents](https://github.com/pipecat-ai/pipecat-subagents) — Distributed multi-agent systems with shared message bus
- [Pipecat Flows](https://github.com/pipecat-ai/pipecat-flows) — Structured conversations with complex state management
- [Pipecat CLI](https://github.com/pipecat-ai/pipecat-cli) — Create, monitor, and deploy projects
- [Whisker](https://github.com/pipecat-ai/whisker) — Real-time Pipecat debugger
- [Tail](https://github.com/pipecat-ai/tail) — Terminal dashboard for Pipecat
- [Voice UI Kit](https://github.com/pipecat-ai/voice-ui-kit) — Beautiful UI components for voice AI
- [Client SDKs](https://docs.pipecat.ai) — JavaScript, React, React Native, Swift, Kotlin, C++, ESP32
- [Community Integrations](https://docs.pipecat.ai/api-reference/server/services/community-integrations) — Shared service integrations

## Getting Started

```bash
# Install with uv
uv add pipecat-ai

# Or with pip
pip install pipecat-ai

# Quickstart
pipecat init quickstart
```

## Examples

- [Foundational examples](https://github.com/pipecat-ai/pipecat/tree/main/examples) — Small snippets introducing one or two concepts
- [Example apps](https://github.com/pipecat-ai/pipecat-examples) — Complete starter applications

## What You Can Build

- Voice Assistants — natural, streaming conversations with AI
- AI Companions — coaches, meeting assistants, characters
- Multimodal Interfaces — voice, video, images, and more
- Interactive Storytelling — creative tools with generative media
- Business Agents — customer intake, support bots, guided flows
- Complex Dialog Systems — design logic with structured conversations

## Recent Release (v1.1.0 — 2026-04-27)

109 releases total. Latest v1.1.0.

---

## Source

- [Raw Source](../../raw/pipecat_20260512.md)
- [GitHub Repository](https://github.com/pipecat-ai/pipecat)
- [Official Documentation](https://docs.pipecat.ai)

## Related Topics

- [Building Agent Apps](../topics/building_agent_apps.md) — Agent Frameworks section

## Community

- [Discord](https://discord.gg/pipecat)
- [X (Twitter)](https://x.com/pipecat_ai)
- [YouTube - Pipecat TV](https://www.youtube.com/playlist?list=PLzU2zoMTQIHjqC3v4q2XVSR3hGSzwKFwH)
