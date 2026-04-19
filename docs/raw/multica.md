# Multica

## Overview

Open-source managed agents platform that turns coding agents into real teammates. Assign tasks via issues, track progress, and build reusable skills over time. Works with Claude Code, Codex, OpenClaw, OpenCode, Hermes, Gemini, Pi, and Cursor Agent.

## Details

- **Org**: multica-ai
- **Stars**: N/A (check GitHub)
- **License**: N/A (check GitHub)

## Key Features

- **Agents as Teammates** — Agents have profiles, appear on the board, post comments, and report blockers proactively
- **Autonomous Execution** — Full task lifecycle management with real-time progress streaming via WebSocket
- **Reusable Skills** — Every solution becomes a reusable skill for the team
- **Unified Runtimes** — One dashboard for all compute (local daemons and cloud runtimes)
- **Multi-Workspace** — Organize work across teams with workspace-level isolation

CLI commands: `multica setup`, `multica daemon start`, `multica issue create`, `multica update`

## Architecture

- Frontend: Next.js 16 (App Router)
- Backend: Go (Chi router, sqlc, gorilla/websocket)
- Database: PostgreSQL 17 with pgvector
- Agent Runtime: Local daemon executing Claude Code, Codex, OpenCode, OpenClaw, Hermes, Gemini, Pi, or Cursor Agent

## Installation

```bash
# macOS / Linux (Homebrew)
brew install multica-ai/tap/multica

# macOS / Linux (install script)
curl -fsSL https://raw.githubusercontent.com/multica-ai/multica/main/scripts/install.sh | bash

# Windows (PowerShell)
irm https://raw.githubusercontent.com/multica-ai/multica/main/scripts/install.ps1 | iex
```

---

*Accessed: 2026-04-18*