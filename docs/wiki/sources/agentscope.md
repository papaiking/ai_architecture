---
title: "AgentScope"
type: "source"
category: "Agent_Frameworks"
tags: ["agentscope", "agent-framework", "multi-agent", "local-deployment", "qwenpaw"]
created: "2026-04-18"
updated: "2026-05-08"
related_topics: ["topics/building_agent_apps.md"]
---

# AgentScope

- **Type**: Agent Framework (bao gồm QwenPaw Personal AI Assistant)

## Overview

AgentScope là framework xây dựng multi-agent system, kèm theo QwenPaw — personal AI assistant dễ cài đặt, deploy local/cloud, kết nối đa kênh, mở rộng qua skills. QwenPaw trước đây là CoPaw.

![AgentScope](../media/agentscope.png)
![AgentScope Logo](../logo.png)

## Details

- **Org**: agentscope-ai (ModelScope)
- **License**: Apache 2.0
- **GitHub**: https://github.com/modelscope/agentscope

## Key Features

- **Multi-Agent Framework** — Xây dựng agent system linh hoạt với inter-agent communication
- **QwenPaw Personal Assistant** — Tích hợp sẵn AI assistant cài local/cloud, đa kênh
- **Local Deployment** — Dữ liệu nằm trên máy, không phụ thuộc bên thứ ba
- **Skills Extension** — Tích hợp sẵn scheduling, PDF/Office processing, news digest; custom skills auto-loaded
- **Multi-Layer Security** — Tool guard, file access control, skill security scanning
- **Local Models** — Hỗ trợ llama.cpp, Ollama, LM Studio (không cần API key)
- **Mission Mode** — Thực thi tác vụ đa giai đoạn tự động
- **ACP Protocol** — Ủy quyền tác vụ cho agent bên ngoài

## QwenPaw: What You Can Do

- **Social media**: Daily hot post digests (Xiaohongshu, Zhihu, Reddit), video summaries
- **Productivity**: Email & newsletter highlights, calendar organization
- **Creative**: Describe goal → auto-execute → wake up to prototype
- **Research**: Track tech & AI news, knowledge base search
- **Desktop**: Organize and search local files, read & summarize documents

## QwenPaw: Installation

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

Then open **http://127.0.0.1:8088/** for the QwenPaw Console.

## Security Features

- **Tool guard** — Intercepts dangerous shell commands
- **File access guard** — Restricts access to sensitive paths
- **Skill security scanning** — Detects prompt injection, command injection, hardcoded keys
- **Local deployment** — All data stored locally
- **Web Authentication** — Optional login protection

## CLI Commands (QwenPaw)

```bash
qwenpaw init --defaults     # Initialize with defaults
qwenpaw app             # Start web UI
qwenpaw doctor           # Diagnostic command
qwenpaw agents create    # CLI agent creation
```

---

## Source

- [Raw Source](../../raw/qwenpaw.md)
- [GitHub AgentScope](https://github.com/modelscope/agentscope)
- [QwenPaw Docs](https://qwenpaw.agentscope.io/)

## Related Topics

- [Building Agent Apps](../topics/building_agent_apps.md)
- [Personal Agents](../topics/personal_agent.md)

## Related Entities

- [AgentScope Team](../entities/agentscope_team.md)