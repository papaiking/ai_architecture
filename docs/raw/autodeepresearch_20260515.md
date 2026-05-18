# Auto-Deep-Research: Your Fully-Automated Personal AI Assistant

**Org**: HKUDS (University of Hong Kong Data Science Lab)
**GitHub**: https://github.com/HKUDS/Auto-Deep-Research
**Stars**: 1.5k
**Forks**: 215
**Commits**: 18
**Language**: Python 100%
**Paper**: https://arxiv.org/abs/2502.05957 (same as AutoAgent)
**Date**: 2026-05-15

---

Auto-Deep-Research is an open-source and cost-efficient alternative to OpenAI's Deep Research, built on the AutoAgent framework by HKUDS. It provides a fully-automated personal AI research assistant that can browse the web, read documents, and generate comprehensive research reports.

## Key Features

- **High Performance**: Delivers good performance on GAIA Benchmark
- **Universal LLM Support**: Integrates with OpenAI, Anthropic, DeepSeek, vLLM, Grok, HuggingFace, Gemini, Groq, OpenRouter
- **Flexible Interaction**: Supports both function-calling and non-function-calling LLMs
- **Cost-Efficient**: Open-source alternative to Deep Research's $200/month subscription - pay-as-you-go with your own LLM API keys
- **File Support**: Handles file uploads for enhanced data interaction
- **One-Click Launch**: Simple `auto deep-research` command - zero configuration needed

## Architecture

Based on a three-agent design inspired by Magentic-one (Microsoft AutoGen):
- Research agents that browse the web and gather information
- Analytical agents for processing and synthesizing findings
- Report generation agents for producing structured outputs

Uses Docker for containerized agent-interactive environment (auto-pulls images based on architecture).

## Quick Start

```bash
conda create -n auto_deep_research python=3.10
conda activate auto_deep_research
git clone https://github.com/HKUDS/Auto-Deep-Research.git
cd Auto-Deep-Research
pip install -e .
# Docker required
# Set API keys in .env file
auto deep-research  # Default: Claude 3.5 Sonnet
```

Supports multiple LLM providers: Anthropic, OpenAI, Mistral, Gemini, HuggingFace, Groq, DeepSeek, OpenRouter, OpenAI-compatible endpoints.

## Relationship to AutoAgent

Auto-Deep-Research is a streamlined version of AutoAgent focused specifically on deep research tasks. It removes non-research components and provides a simpler one-click experience. AutoAgent is the underlying framework that enables Auto-Deep-Research.
