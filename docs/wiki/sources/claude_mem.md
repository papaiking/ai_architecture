---
title: "Claude-Mem"
type: "source"
category: "Builder_agents"
tags: ["memory", "persistence", "compression", "context-management", "builder-agent"]
created: "2026-04-18"
updated: "2026-04-18"
related_topics: ["topics/builder_agents.md"]
---

# Claude-Mem

**Type**: Persistent Memory System

## Overview

Claude-Mem is a persistent memory compression system for Claude Code that automatically captures everything Claude does during coding sessions, compresses it with AI using Claude's agent-sdk, and injects relevant context back into future sessions. This enables Claude to maintain continuity of knowledge about projects even after sessions end.

## Details

- Org: thedotmack
- Stars: 61.9k
- License: AGPL-3.0
- Releases: 232
- Language: TypeScript (83.2%), JavaScript (11%), Shell (3%)
- Forked by: 5.1k

## Key Features

- Persistent memory across sessions
- Automatic observation capture and AI compression
- Progressive disclosure with token cost visibility
- Skill-based natural language search (mem-search)
- Web viewer UI at http://localhost:37777
- 3-layer workflow for ~10x token savings
- Privacy control with <private> tags
- Multiple IDE support: Claude Code, Gemini CLI, OpenCode
- Claude Desktop plugin
- OpenClaw gateway integration
- Endless Mode (beta) for extended sessions
- Vector search with Chroma database
- SQLite storage with FTS5 search

## Installation

```bash
# For Claude Code
npx claude-mem install

# For Gemini CLI
npx claude-mem install --ide gemini-cli

# For OpenCode
npx claude-mem install --ide opencode

# Inside Claude Code
/plugin marketplace add thedotmack/claude-mem
/plugin install claude-mem

# For OpenClaw
curl -fsSL https://install.cmem.ai/openclaw.sh | bash
```

## Core Components

1. **5 Lifecycle Hooks** - SessionStart, UserPromptSubmit, PostToolUse, Stop, SessionEnd
2. **Worker Service** - HTTP API on port 37777 with web viewer
3. **SQLite Database** - Stores sessions, observations, summaries
4. **mem-search Skill** - Natural language queries
5. **Chroma Vector Database** - Hybrid semantic + keyword search

## MCP Search Tools (3-Layer Workflow)

```javascript
// Step 1: Search for index (~50-100 tokens)
search(query="authentication bug", type="bugfix", limit=10)

// Step 2: Get chronological context
timeline(observation_id=123)

// Step 3: Fetch full details (~500-1000 tokens)
get_observations(ids=[123, 456])
```

Three-layer workflow achieves ~10x token savings by filtering before fetching details.

## Configuration

Settings in `~/.claude-mem/settings.json`:

```json
{
  "CLAUDE_MEM_MODE": "code",        // or "code--zh", "code--ja"
  "CLAUDE_MEM_WORKER_PORT": 37777,
  "CLAUDE_MEM_DATA_DIR": "~/.claude-mem"
}
```

## System Requirements

- Node.js 18.0.0+
- Claude Code (latest)
- Bun (auto-installed)
- uv (auto-installed for vector search)
- SQLite 3

## Web Viewer

- Memory stream: http://localhost:37777
- API: http://localhost:37777/api/observation/{id}

## Beta Features

- **Endless Mode** - Biomimetic memory architecture for extended sessions
- Switch via web viewer UI → Settings

## Related Entities

- [Claude Code](https://claude.com/claude-code) - IDE integration
- [Chroma](https://github.com/chroma-core/chroma) - Vector database
- [OpenClaw](https://openclaw.ai) - Gateway integration
- [mem0](https://github.com mem0) - Alternative memory solution

---

## Nguồn

- raw/claude_mem.md

## Liên kết liên quan

- [Builder Agents](../topics/builder_agents.md)
- [Alex Newman](../entities/thedotmack.md)