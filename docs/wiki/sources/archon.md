---
title: "Archon - Workflow Engine for Coding Agent"
type: "source"
category: "Builder_agents"
tags: ["workflow", "engine", "coding", "agent", "mcp", "orchestrator"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["raw/archon.md"]
related_topics: ["topics/builder_agents.md", "topics/orchestrator_agent.md"]
---

# Archon - Workflow Engine for Coding Agent

**Author**: coleam00

## Overview

"Command center" cho AI coding assistant, hoạt động như MCP server để quản lý knowledge, làm RAG nâng cao và quản lý task/workflow.

## Key Features

- **Workflow Engine**: Định nghĩa dev pipeline bằng YAML (planning → implementation → test → code review → PR)
- **Knowledge Base & RAG**: Crawl website, upload PDF/docs, index cho AI code assistant
- **MCP Server**: Expose tools cho Claude Code, Cursor, Windsurf, Kiro...
- **Task Management**: Gắn task với docs, file, repo cụ thể

## Kiến trúc

```
┌─────────────────────────────────────────────────────────┐
│  Platform Adapters (Web UI, CLI, Telegram, Slack,       │
│                    Discord, GitHub)                      │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                     Orchestrator                        │
│          (Message Routing & Context Management)         │
└─────────────┬───────────────────────────┬───────────────┘
              │                           │
      ┌───────┴────────┐          ┌───────┴────────┐
      │                │          │                │
      ▼                ▼          ▼                ▼
┌───────────┐  ┌────────────┐  ┌──────────────────────────┐
│  Command  │  │  Workflow  │  │    AI Assistant Clients  │
│  Handler  │  │  Executor  │  │      (Claude / Codex)    │
│  (Slash)  │  │  (YAML)    │  │                          │
└───────────┘  └────────────┘  └──────────────────────────┘
      │              │                      │
      └──────────────┴──────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│              SQLite / PostgreSQL (7 Tables)             │
│   Codebases • Conversations • Sessions • Workflow Runs  │
│    Isolation Environments • Messages • Workflow Events  │
└─────────────────────────────────────────────────────────┘
```

### Database Schema (7 Tables)

| Table | Mô tả |
|-------|-------|
| Codebases | Quản lý projects/repos |
| Conversations | Lịch sử chat |
| Sessions | Phiên làm việc |
| Workflow Runs | Trạng thái workflow |
| Isolation Environments | Môi trường tách biệt |
| Messages | Tin nhắn/logs |
| Workflow Events | Event history cho từng node |

## Bộ tools cho coding agents

Archon đứng giữa LLM và project, cung cấp:

- Danh sách project, features, tasks
- Knowledge base đã index (docs, web, PDF, code examples)
- Workflow YAML định nghĩa sẵn
- Agents Service + Agent Work Orders cho orchestration

## Knowledge Management

- **Crawl docs/web**: Auto detect sitemap, trích code example, semantic search
- **Upload file**: PDF, Word, markdown, text với metadata
- **Query context**: Vector search + reranking trả chunk phù hợp nhất

## Project & Task Management

- **Cấu trúc**: Project → Feature/Epic → Task
- **AI-assisted creation**: LLM đề xuất task từ yêu cầu
- **Task ↔ Workflow**: Mỗi task gắn với workflow YAML (fix-bug, build-feature, update-docs)
- **Real-time tracking**: Status, log, artefact được cập nhật liên tục

## Ai chạy task?

| Thành phần | Vai trò |
|-----------|---------|
| Archon (workflow engine) | Thực thi DAG workflow, gọi LLM, giữ state |
| Coding assistant (Claude/Cursor) | UI: hiển thị conversation, approve, xem log |

**Trạng thái**:
- Workflow tracking: event history cho từng node (started, completed, failed)
- Rerun: skip node đã hoàn thành
- Task ↔ Workflow: tự động sync trạng thái

## So sánh với Claude Code

| Claude Code | Archon |
|------------|--------|
| CLI tool đơn lẻ | Workflow engine có web UI |
| Chat ad-hoc | Deterministic and repeatable |
| Memory thủ công | Knowledge base tự động |

---

## Related Topics

- [Builder Agents](../topics/builder_agents.md)
- [Orchestrator Agent](../topics/orchestrator_agent.md)

---

## Source

- [Raw Source](../../raw/archon.md)
- [GitHub](https://github.com/coleam00/archon)