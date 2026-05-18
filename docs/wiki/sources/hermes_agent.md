---
title: "Hermes Agent"
type: "source"
category: "Personal_agents"
tags: ["personal-agent", "self-improving", "learning-loop", "messaging-gateway"]
created: "2026-04-18"
updated: "2026-04-18"
related_topics: ["topics/personal_agent.md"]
---

# Hermes Agent

- **Type**: Personal AI Agent

## Overview

Hermes Agent is a self-improving AI agent built by Nous Research. It's the only agent with a built-in learning loop - creating skills from experience, improving them during use, searching past conversations, and building a deepening model of the user across sessions. It runs on a $5 VPS, cloud VMs, or serverless infrastructure with near-zero idle cost.

## Details

- Org: NousResearch
- Stars: 98k
- License: MIT
- Commits: 4,770+
- Contributors: 496+

## Key Features

- Built-in learning loop with autonomous skill creation
- Persistent memory with periodic nudges and FTS5 session search
- Honcho dialectic user modeling for cross-session recall
- Skills system that self-improves during use
- 40+ built-in tools
- Multiple terminal backends: local, Docker, SSH, Daytona, Singularity, Modal
- Messaging gateway: Telegram, Discord, Slack, WhatsApp, Signal, Email
- Full TUI with multiline editing, slash-commands, conversation history
- Cron scheduler for automated tasks
- MCP integration for extended capabilities
- Multi-model support: Nous Portal, OpenRouter (200+ models), NVIDIA NIM, OpenAI, Anthropic, Google, Hugging Face

## Quick Start

```bash
# Install
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash

# Start chatting
hermes

# Configure model
hermes model          # Interactive model selection
hermes model openai/gpt-5.4

# Configure tools
hermes tools

# Start messaging gateway
hermes gateway setup
hermes gateway start
```

## CLI Commands

```bash
hermes                  # Interactive CLI
hermes model            # Choose LLM provider
hermes tools            # Configure tools
hermes config set       # Set config values
hermes gateway          # Start messaging gateway
hermes setup           # Full setup wizard
hermes update          # Update to latest
hermes doctor          # Diagnose issues
```

## Slash Commands (CLI & Messaging)

| Action | Command |
|--------|---------|
| New conversation | /new or /reset |
| Change model | /model [provider:model] |
| Set personality | /personality [name] |
| Retry/undo | /retry, /undo |
| Compress context | /compress |
| Check usage | /usage, /insights [--days N] |
| Browse skills | /skills, /<skill-name> |

## Platform Support

- **Terminal backends**: local, Docker, SSH, Daytona, Singularity, Modal
- **Messaging platforms**: Telegram, Discord, Slack, WhatsApp, Signal, Email, Home Assistant

## Migration from OpenClaw

```bash
hermes claw migrate              # Interactive migration
hermes claw migrate --dry-run # Preview
hermes claw migrate --preset user-data
```

## Skills System

Hermes creates skills autonomously after complex tasks. Skills:
- Automatically persist knowledge
- Self-improve during use
- Compatible with agentskills.io open standard

## Architecture

- Six terminal backends for environment management
- Messaging gateway for cross-platform continuity
- Honcho for user modeling
- MCP server for external tool integration
- SQLite for persistent storage

## Related Entities

- [Nous Research](https://nousresearch.com) - Creator organization
- [OpenClaw](https://github.com/openclaw) - Previous version
- [Honcho](https://github.com/plastic-labs/honcho) - User modeling
- [agentskills.io](https://agentskills.io) - Open skill standard

---

## Source

- [Raw Source](../../raw/hermes_agent.md)
- [GitHub](https://github.com/nousresearch/hermes-agent)

## Related Topics

- [Personal Agents](../topics/personal_agent.md)
- [Nous Research](../entities/nous_research.md)