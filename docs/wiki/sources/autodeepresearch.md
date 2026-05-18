---
title: "Auto-Deep-Research"
type: "source"
category: "Research_agents"
tags: ["deep-research", "autoagent", "hku", "research-assistant", "web-browsing", "cost-efficient"]
created: "2026-05-15"
updated: "2026-05-15"
related_topics: ["topics/Research_agents.md"]
sources: ["raw/autodeepresearch_20260515.md"]
---

# Auto-Deep-Research

**Source:** [github.com/HKUDS/Auto-Deep-Research](https://github.com/HKUDS/Auto-Deep-Research)
**Stars:** 1.5k | **Forks:** 215 | **Commits:** 18
**Language:** Python | **Paper:** [arxiv.org/abs/2502.05957](https://arxiv.org/abs/2502.05957)

![Auto-Deep-Research Logo](../media/autodeepresearch_logo.jpg)

Your Fully-Automated Personal AI Assistant — open-source, cost-efficient alternative to OpenAI's Deep Research, built on [AutoAgent](https://github.com/HKUDS/AutoAgent).

[GitHub](https://github.com/HKUDS/Auto-Deep-Research) | [Paper](https://arxiv.org/abs/2502.05957) | [Slack](https://join.slack.com/t/metachain-workspace/shared_invite/zt-2zibtmutw-v7xOJObBf9jE2w3x7nctFQ)

## Overview

Auto-Deep-Research is a streamlined, focused version of AutoAgent that provides a fully-automated deep research experience. It serves as the first ready-to-use product built on the AutoAgent framework, demonstrating how to create powerful agent apps with minimal effort.

## Key Features

- **One-Click Launch** — `auto deep-research` command, zero configuration
- **Universal LLM** — Supports OpenAI, Anthropic, DeepSeek, Gemini, Grok, HuggingFace, Groq, OpenRouter
- **Cost-Efficient** — Pay-as-you-go alternative to $200/month Deep Research subscription
- **File Upload** — Handle documents for enhanced data interaction
- **Docker-Based** — Auto-pulls container images based on architecture
- **GAIA Benchmark** — Competitive performance on GAIA evaluation

## Quick Start

```bash
conda create -n auto_deep_research python=3.10
conda activate auto_deep_research
git clone https://github.com/HKUDS/Auto-Deep-Research.git
cd Auto-Deep-Research && pip install -e .
# Set ANTHROPIC_API_KEY in .env
auto deep-research
```

## Nguồn

- [Raw Source](../../raw/autodeepresearch_20260515.md)
- [GitHub Repository](https://github.com/HKUDS/Auto-Deep-Research)
- [Paper](https://arxiv.org/abs/2502.05957)

## Liên kết liên quan

- [Research Agents](../topics/Research_agents.md)
- [AutoAgent](../sources/autoagent.md) — Underlying framework
