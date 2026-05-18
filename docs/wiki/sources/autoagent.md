---
title: "AutoAgent"
type: "source"
category: "Building_AI_applications"
tags: ["autoagent", "metachain", "zero-code", "agent-framework", "deep-research", "nlp", "hku"]
created: "2026-05-14"
updated: "2026-05-14"
related_topics: ["topics/building_agent_apps.md"]
sources: ["raw/autoagent_20260514.md"]
---

# AutoAgent

- **Source:** [github.com/HKUDS/AutoAgent](https://github.com/HKUDS/AutoAgent)
- **Stars:** 9.3k | **License:** MIT | **Forks:** 1.3k | **Commits:** 109
- **Language:** Python | **Paper:** [arxiv.org/abs/2502.05957](https://arxiv.org/abs/2502.05957)

![AutoAgent Logo](../media/autoagent_logo.svg)

Fully-Automated & Zero-Code LLM Agent Framework by HKU Data Science Lab. Create and deploy agents through natural language alone — no coding required.

[GitHub](https://github.com/HKUDS/AutoAgent) | [Paper](https://arxiv.org/abs/2502.05957) | [Site](https://autoagent-ai.github.io) | [Discord](https://discord.gg/jQJdXyDB) | [Slack](https://join.slack.com/t/metachain-workspace/shared_invite/zt-2zibtmutw-v7xOJObBf9jE2w3x7nctFQ)

## Overview

AutoAgent (formerly MetaChain, v0.2.0) is a fully-automated framework for creating LLM agents through natural language. It features three operation modes: **User Mode** (ready-to-use deep research), **Agent Editor** (custom agent creation without workflow), and **Workflow Editor** (multi-agent workflow creation). Supports any LLM provider through LiteLLM integration.

## Key Features

- **Natural Language-Driven** — Build agents purely through dialogue, zero coding needed
- **Deep Research Mode** — Multi-agent research system matching Deep Research performance
- **Self-Developing** — AutoAgent can modify and improve itself iteratively
- **Docker-Based** — Containerized agent-interactive environment, auto-pulls images
- **Multi-LLM Support** — Anthropic, OpenAI, Mistral, Gemini, HuggingFace, Groq, DeepSeek, OpenRouter
- **Tool Creation** — Create custom tools on the fly through natural language

## Quick Start

```bash
git clone https://github.com/HKUDS/AutoAgent.git
cd AutoAgent && pip install -e .
# Set ANTHROPIC_API_KEY in .env
auto main
```

## Nguồn

- [Raw Source](../../raw/autoagent_20260514.md)
- [GitHub Repository](https://github.com/HKUDS/AutoAgent)
- [Paper](https://arxiv.org/abs/2502.05957)

## Liên kết liên quan

- [Building Agent Apps](../topics/building_agent_apps.md)
