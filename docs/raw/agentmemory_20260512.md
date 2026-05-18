# agentmemory

## Overview

**agentmemory** is the #1 persistent memory for AI coding agents based on real-world benchmarks. 95.2% retrieval R@5, 92% fewer tokens, 51 MCP tools, 12 auto hooks, 0 external databases. Built on iii-engine.

- **Org**: rohitg00
- **GitHub**: https://github.com/rohitg00/agentmemory
- **Stars**: 6.5k
- **License**: Apache-2.0
- **npm**: @agentmemory/agentmemory
- **Website**: https://agent-memory.dev

## Key Features

- **Automatic Capture** — 12 hooks silently record every tool use, no manual effort
- **Hybrid Search** — BM25 + Vector + Knowledge Graph with RRF fusion (95.2% R@5 on LongMemEval-S)
- **4-Tier Memory Consolidation** — Working → Episodic → Semantic → Procedural
- **51 MCP Tools** — memory_recall, memory_save, memory_smart_search, memory_sessions, etc.
- **12 Auto Hooks** — SessionStart, UserPromptSubmit, PreToolUse, PostToolUse, Stop, etc.
- **No External DBs** — SQLite + iii-engine, zero dependencies
- **Privacy First** — Strips secrets, API keys before storage
- **Memory Lifecycle** — TTL expiry, contradiction detection, importance eviction
- **Real-Time Viewer** — Live observation stream, session explorer, memory browser on port 3113

## Benchmarks

| Metric | agentmemory | Competitors |
|--------|-------------|-------------|
| Retrieval R@5 | **95.2%** | 68.5% (mem0), 83.2% (Letta) |
| Retrieval R@10 | **98.6%** | — |
| MRR | **88.2%** | — |
| Tokens/session | **~1,900** ($10/yr) | 22K+ at 240 obs |
| vs BM25-only | **+9pp** R@5 | — |

## Works With

Claude Code, Cursor, Gemini CLI, Codex CLI, OpenClaw, Hermes, Cline, Roo Code, Windsurf, Goose, Aider, Claude Desktop, Kilo Code, OpenCode, pi, and any MCP client.

## Quick Start

```bash
# Start the memory server
npx @agentmemory/agentmemory

# Seed demo data
npx @agentmemory/agentmemory demo

# Open viewer
open http://localhost:3113
```

## MCP Server

```json
{
  "mcpServers": {
    "agentmemory": {
      "command": "npx",
      "args": ["-y", "@agentmemory/mcp"],
      "env": {
        "AGENTMEMORY_URL": "http://localhost:3111"
      }
    }
  }
}
```

---

*Accessed: 2026-05-12*
