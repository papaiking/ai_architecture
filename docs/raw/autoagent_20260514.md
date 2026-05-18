# AutoAgent: Fully-Automated & Zero-Code LLM Agent Framework

**Org**: HKUDS (University of Hong Kong Data Science Lab)
**GitHub**: https://github.com/HKUDS/AutoAgent
**License**: MIT
**Stars**: 9.3k
**Forks**: 1.3k
**Commits**: 109
**Language**: Python 99.8%
**Paper**: https://arxiv.org/abs/2502.05957
**Website**: https://autoagent-ai.github.io
**Date**: 2026-05-14

---

AutoAgent (formerly MetaChain) is a fully-automated and highly self-developing framework that enables users to create and deploy LLM agents through Natural Language Alone. No coding required.

## Key Features

- **Natural Language-Driven Agent Building** — Automatically constructs and orchestrates collaborative agent systems purely through natural dialogue
- **Zero-Code Framework** — Anyone can create and customize agents, tools, and workflows using natural language alone
- **Self-Managing Workflow Generation** — Dynamically creates, optimizes and adapts agent workflows from high-level task descriptions
- **Intelligent Resource Orchestration** — Controlled code generation for tools, agents, and workflows through iterative self-improvement
- **Self-Play Agent Customization** — Supports both single agent creation and multi-agent workflow generation

## Usage Modes

### User Mode (Deep Research Agents)
Ready-to-use multi-agent system for information retrieval, complex analytical tasks, and comprehensive report generation. Matches Deep Research performance using Claude 3.5. Compatible with any LLM (DeepSeek-R1, Grok, Gemini, etc.). Open-source alternative to $200/month Deep Research.

### Agent Editor (Agent Creation without Workflow)
Create custom agents through natural language conversation:
1. Describe what kind of agent you want
2. Auto-generated agent profiling
3. Create desired tools
4. Agent is ready to use

### Workflow Editor (Agent Creation with Workflow)
Create multi-agent workflows through natural language description. Dynamically generates orchestrated agent pipelines.

## Quick Start

```bash
git clone https://github.com/HKUDS/AutoAgent.git
cd AutoAgent
pip install -e .
# Docker required for agent-interactive environment
# Set API keys in .env file
auto main  # Start with Claude 3.5 (default)
# Or with other models:
COMPLETION_MODEL=gpt-4o auto main
```

## Supported LLM Providers
Anthropic, OpenAI, Mistral, Gemini, HuggingFace, Groq, DeepSeek, OpenRouter, OpenAI-compatible endpoints (Grok, etc.)

## Todo
- SWE-bench, WebArena benchmarks
- GUI agent with Computer-Use
- Composio tool platform integration
- E2B code sandbox support
- Web GUI interface
