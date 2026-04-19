---
title: "QwenPaw"
type: "source"
category: "Personal_agents"
tags: ["personal-agent", "ai-assistant", "local-deployment", "multi-agent"]
created: "2026-04-18"
updated: "2026-04-18"
related_topics: ["topics/personal_agent.md"]
---

# QwenPaw

**Type**: Personal AI Assistant

## Overview

Personal AI assistant — easy to install, deploy locally or in the cloud, connect across channels, extend with skills. Formerly known as CoPaw. Built by AgentScope team.

## Details

- **Org**: agentscope-ai
- **License**: Apache 2.0

## Key Features

- **Local Deployment** — Memory and data fully under your control; no third-party hosting
- **Skills Extension** — Built-in scheduling, PDF/Office processing, news digest; custom skills auto-loaded
- **Multi-Agent Collaboration** — Create multiple independent agents with inter-agent communication
- **Multi-Layer Security** — Tool guard, file access control, skill security scanning
- **Multi-Channel** — DingTalk, Feishu, WeChat, Discord, Telegram, and more
- **Local Models** — Supports llama.cpp, Ollama, LM Studio (no API key needed)
- **Mission Mode** — Autonomous multi-phase task execution
- **ACP Protocol** — External agent delegation

## What You Can Do

- **Social media**: Daily hot post digests (Xiaohongshu, Zhihu, Reddit), video summaries
- **Productivity**: Email & newsletter highlights, calendar organization
- **Creative**: Describe goal → auto-execute → wake up to prototype
- **Research**: Track tech & AI news, knowledge base search
- **Desktop**: Organize and search local files, read & summarize documents

## Installation

```bash
# Option 1: pip install
pip install qwenpaw
qwenpaw init --defaults
qwenpaw app

# Option 2: Script install (macOS/Linux)
curl -fsSL https://qwenpaw.agentscope.io/install.sh | bash

# Option 3: Docker
docker pull agentscope/qwenpaw:latest
docker run -p 127.0.0.1:8088:8088 \
  -v qwenpaw-data:/app/working \
  agentscope/qwenpaw:latest
```

Then open **http://127.0.0.1:8088/** for the Console.

## Security Features

- **Tool guard** — Intercepts dangerous shell commands
- **File access guard** — Restricts access to sensitive paths
- **Skill security scanning** — Detects prompt injection, command injection, hardcoded keys
- **Local deployment** — All data stored locally
- **Web Authentication** — Optional login protection

## CLI Commands

```bash
qwenpaw init --defaults     # Initialize with defaults
qwenpaw app             # Start web UI
qwenpaw doctor           # Diagnostic command
qwenpaw agents create    # CLI agent creation
```

---

## Nguồn

- raw/qwenpaw.md

## Liên kết liên quan

- [Personal Agents](../topics/personal_agent.md)
- [AgentScope Team](../entities/agentscope_team.md)