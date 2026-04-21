---
title: "Archon - Workflow Engine for Coding Agent"
type: "source"
category: "Builder_agents"
tags: ["workflow", "engine", "coding", "agent", "mcp", "orchestrator"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["https://github.com/coleam00/archon"]
---

# Archon - Workflow Engine for Coding Agent

**Author**: coleam00
**License**: Apache-2.0

## Overview

Archon là một "command center" cho AI coding assistant, hoạt động như MCP server để quản lý knowledge (docs, website, file), làm RAG nâng cao và quản lý task/workflow cho các project code.

---

## Archon là gì, dùng để làm gì?

Archon là một workflow engine cho AI coding agents: bạn định nghĩa quy trình dev (planning, implementation, validation, code review, PR, v.v.) bằng YAML workflow, rồi để AI agent chạy theo quy trình đó.

- **Về phía bạn**: đây là một web interface để quản lý knowledge base (docs, website crawl, PDF, code), ngữ cảnh và task trong project.
- **Về phía AI**: Archon đóng vai trò như một MCP server để các client như Claude Code, Cursor, Windsurf, Kiro, Claude Desktop… truy cập chung vào cùng knowledge, context và task.

**Mục tiêu chính**: làm cho quá trình AI coding "deterministic and repeatable" – bạn có thể đóng gói một quy trình coding chuẩn, sau đó AI cứ thế lặp lại cho các feature/bug mới.

**Ví dụ**: bạn có thể định nghĩa một workflow "build feature mới" gồm bước hiểu yêu cầu, đọc docs liên quan, tạo branch, generate code, tự test, mở PR; sau đó gọi workflow này từ Claude Code để nó chạy "harness" đó trên repo của bạn.

---

## 1. Bộ tools cho các coding agents

Archon là một MCP server + workflow engine đứng giữa LLM (Claude, Cursor, Gemini CLI, v.v.) và project của bạn.

Các coding agent (Claude Code, Cursor, Kiro, Gemini CLI…) kết nối tới Archon qua MCP, giống như một "backend chung" cho kiến thức và task.

Khi đó agent không chỉ thấy "một folder code" + "history đoạn chat", mà còn thấy:
- Danh sách project, tính năng, task
- Knowledge base (docs, web, PDF, code examples) đã index trong Archon
- Các workflow YAML mà bạn định nghĩa sẵn (ví dụ workflow để tạo PR, fix bug, update docs)

Archon cũng có phần "Agents Service" và "Agent Work Orders" để thực thi workflow, chạy nhiều step/agent song song, theo dõi trạng thái, stream log… thay vì bạn phải tự viết orchestration.

**Ví dụ**: bạn gọi từ Claude Code một workflow "idea-to-PR", Archon sẽ quản lý toàn bộ DAG các bước (phân tích yêu cầu, tạo nhánh, sửa code, chạy test, tạo PR) và cho agent xem đúng context/knowledge cần thiết từng bước.

---

## 2. Thêm context/knowledge như thế nào?

Phần "Knowledge Management" trong Archon:

### Crawl docs/web
- Nhập URL docs, Archon sẽ tự detect sitemap, crawl nhiều page, trích code example, chunk + embed để làm semantic search

### Upload file
- Upload PDF, Word, markdown, text… Archon sẽ xử lý, cắt đoạn hợp lý, embed và lưu metadata (source, type, tag…)

### Quản lý theo nguồn
- Mỗi nguồn (website, repo docs, file) trở thành một "knowledge source" với tag, type, để bạn lọc và gắn vào project/task

### Khi coding agent làm việc thông qua Archon
- Nó query context qua Archon, thay vì tự "lục code + internet" ngẫu nhiên
- Archon sẽ dùng vector search, reranking và metadata để trả ra những chunk docs/code phù hợp nhất
- Bạn (hoặc agent) có thể link trực tiếp một knowledge entry vào task cụ thể

**Điểm quan trọng**: Archon biến knowledge của bạn thành một "project brain" có cấu trúc, để nhiều agent khác nhau (Claude, Gemini, v.v.) dùng chung qua MCP, không phụ thuộc vào client UI nào.

---

## 3. Quản lý task trong project

### Cấu trúc project
- **Cấp 1**: Project (ứng dụng chính, repo chính)
- **Cấp 2**: Feature / Epic (tính năng hoặc mảng lớn)
- **Cấp 3**: Task (việc cụ thể mà agent hoặc con người sẽ làm)

Mỗi task có: mô tả, trạng thái, liên kết tới repo/project, knowledge liên quan, và có thể gắn với workflow nhất định.

### Cách tạo và quản lý task
- **AI-assisted creation**: bạn mô tả high-level yêu cầu, Archon dùng LLM để tự đề xuất danh sách task, breakdown thành subtasks
- Tạo/chỉnh task trong UI hoặc từ coding agent qua MCP
- Task có progress tracking realtime: khi workflow/agent làm việc, Archon cập nhật status, log, kết quả…

### Liên kết task ↔ workflow ↔ agent
Mỗi task có thể gắn với một workflow YAML nhất định:
- Workflow "fix-bug" cho task bug
- Workflow "build-feature" cho task feature
- Workflow "update-docs" cho task tài liệu

Khi bạn bảo coding agent "làm task này", Archon sẽ:
1. Khởi động workflow tương ứng cho task đó
2. Load knowledge liên quan
3. Thực thi các bước LLM
4. Track tiến độ, log, artefact và update trạng thái task

---

## 4. Ai chạy task? Archon hay coding agent?

### Phân chia trách nhiệm

| Thành phần | Vai trò |
|-----------|---------|
| Workflow engine + Agent Work Orders | Định nghĩa DAG workflow (YAML), điều phối từng node |
| Coding assistant client | UI + MCP client: hiển thị conversation, chuyển lệnh tới Archon |

**Về mặt kỹ thuật**:
- Execution chính diễn ra trong Archon (agents service/worker), không phải trong editor client
- Coding assistant đóng vai trò: khởi động workflow, trả lời các bước cần input người dùng, hiển thị log/kết quả

### Tracking trạng thái

**Workflow tracking**:
- Mỗi lần chạy workflow, Archon ghi event history cho từng node (node_started, node_completed, node_failed…)
- Khi rerun cùng workflow, Archon sẽ load lại node_completed từ run trước và skip những node đã hoàn thành

**Task ↔ Workflow mapping**:
- Task chứa metadata + liên kết tới repo + knowledge sources + workflow runs liên quan
- Khi run update trạng thái (RUNNING → COMPLETED/FAILED), task cũng được cập nhật tương ứng

### Coding agent đang làm gì?

Workflow của một task gồm nhiều loại step:
- **Suy nghĩ / tạo kế hoạch**: Archon gửi prompt tới LLM và ghi output
- **Chỉnh sửa code**: Archon gọi MCP tool để patch file hoặc hướng dẫn bạn thực hiện
- **Chạy test/command**: Archon gọi npm test, pytest…, lưu kết quả
- **Approval gate**: Archon gửi message yêu cầu approve/reject trước khi tiếp tục

---

## Architecture

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

### Components

| Component | Mô tả |
|-----------|-------|
| Platform Adapters | Web UI, CLI, Telegram, Slack, Discord, GitHub |
| Orchestrator | Message routing & context management |
| Command Handler | Xử lý slash commands |
| Workflow Executor | Chạy YAML-defined workflows |
| AI Assistant Clients | Claude, Codex, Gemini... |
| Database | SQLite/PostgreSQL với 7 tables |

### Database Schema (7 Tables)

- **Codebases**: Quản lý projects/repos
- **Conversations**: Lịch sử chat
- **Sessions**: Phiên làm việc
- **Workflow Runs**: Trạng thái workflow execution
- **Isolation Environments**: Môi trường tách biệt
- **Messages**: Tin nhắn/logs
- **Workflow Events**: Event history cho từng node

---

## Kiến trúc & Services

| Service | URL | Mô tả |
|---------|-----|-------|
| archon-ui | localhost:3737 | Web Interface (React, TypeScript, TailwindCSS) |
| archon-server | localhost:8181 | API Service: web crawling, xử lý docs/PDF, RAG |
| archon-mcp | localhost:8051 | MCP Server: expose tools cho Claude Code, Cursor... |
| archon-agents | localhost:8052 | Agents Service: reranking, RAG nâng cao, LLM orchestration |
| archon-agent-work-orders | localhost:8053 | Workflow execution engine (optional) |

---

## Cài đặt

**Prerequisites:**
- Docker Desktop
- Node.js 18+
- Supabase account
- OpenAI API key

**Clone & setup:**
```bash
git clone -b stable https://github.com/coleam00/archon.git
```

---

## So sánh với Claude Code

| Claude Code | Archon |
|------------|--------|
| CLI tool đơn lẻ | Workflow engine có web UI |
| Memory file thủ công | Knowledge base tự động crawl |
| Chat ad-hoc | Deterministic and repeatable workflows |
| Local only | MCP server + cloud options |

---

## Source

- [Wiki Source](../wiki/sources/archon.md)
- [GitHub](https://github.com/coleam00/archon)