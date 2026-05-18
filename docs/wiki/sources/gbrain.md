---
title: "GBrain"
type: "source"
category: "Personal_agents"
tags: ["personal-agent", "knowledge-graph", "memory", "ai-agent", "hybrid-search", "mcp"]
created: "2026-05-12"
updated: "2026-05-12"
related_topics: ["topics/personal_agent.md", "topics/building_agent_apps.md"]
---

# GBrain

- **Type**: AI Agent Memory & Knowledge System  
- **Slogan**: Your AI agent is smart but forgetful. GBrain gives it a brain.

Personal knowledge and memory system for AI agents built by **Garry Tan** (President & CEO of Y Combinator). Powers his production OpenClaw deployment: 17,888 pages, 4,383 people, 723 companies, 21 cron jobs running autonomously.

## Details

- **Author**: Garry Tan (President & CEO of Y Combinator)
- **License**: MIT
- **GitHub**: [https://github.com/garrytan/gbrain](https://github.com/garrytan/gbrain)
- **Stars**: 15.3k+
- **Evals Repo**: [gbrain-evals](https://github.com/garrytan/gbrain-evals)
- **Install**: OpenClaw, Hermes Agent, or standalone
- **Ecosystem**: [GStack](https://github.com/garrytan/gstack) — coding engine (70k+ stars)

## Key Features

- **Self-Wiring Knowledge Graph** — Every page write extracts entity references and creates typed links (`attended`, `works_at`, `invested_in`, `founded`, `advises`) with zero LLM calls
- **Hybrid Search** — Vector + keyword + RRF (Reciprocal Rank Fusion), with backlink-boosted ranking
- **PGLite** — In-browser Postgres, database ready in 2 seconds, no server required
- **34 Skills** — Organized by resolver pattern; skills encode complete workflows
- **MCP Server** — 30+ tools via stdio or HTTP with OAuth 2.1 (ChatGPT, Claude Desktop, Cursor, etc.)
- **Minions** — Durable Postgres-native job queue for deterministic background work, 753ms vs gateway timeout
- **Durable Agents** — Subagent runs survive crashes, replay from last committed turn
- **Skillify** — Turn failures into permanent skills with a 10-item audit checklist
- **Storage Tiering** — Keep bulk content out of git, auto-managed `.gitignore`
- **BrainBench** — P@5 49.1%, R@5 97.9% on 240-page corpus

## The 34 Skills

| Category | Skills |
|----------|--------|
| **Always-on** | signal-detector, brain-ops |
| **Content Ingestion** | ingest, idea-ingest, media-ingest, meeting-ingestion, voice-note-ingest, article-enrichment |
| **Research & Synthesis** | book-mirror, strategic-reading, concept-synthesis, perplexity-research, archive-crawler, academic-verify, brain-pdf |
| **Brain Operations** | enrich, query, maintain, citation-fixer, repo-architecture, publish, data-research |
| **Operational** | daily-task-manager, daily-task-prep, cron-scheduler, reports, cross-modal-review, webhook-transforms, testing, skill-creator, skillify, skillpack-check, smoke-test, minion-orchestrator |
| **Identity & Setup** | soul-audit, setup, migrate, briefing |

## Getting Data In

- **Recipes**: Voice-to-Brain (Twilio + OpenAI Realtime), Email-to-Brain (Gmail), X-to-Brain, Calendar-to-Brain, Meeting Sync, Public Tunnel (ngrok), Credential Gateway
- **Migration**: Obsidian, Notion, Logseq, markdown, CSV, JSON, Roam
- **Data Research**: Extract structured data (MRR, ARR, runway, headcount) from email with parameterized YAML recipes

## How It Works

```
Signal arrives (meeting, email, tweet, link)
  → Signal detector captures ideas + entities (parallel, never blocks)
  → Brain-ops: check brain first (gbrain search, gbrain get)
  → Respond with full context
  → Write: update brain pages + citations
  → Auto-link: typed relationships extracted on every write (zero LLM calls)
  → Sync: gbrain indexes changes for next query
```

## Architecture

```
Brain Repo (markdown files = source of truth) ←→ GBrain (Postgres + pgvector) ←→ AI Agent (34 skills, RESOLVER.md)
```

Human always wins — edit any markdown file and `gbrain sync` picks up changes.

## Quick Start

```bash
# Install on agent platform (recommended)
# Paste into OpenClaw or Hermes:
# "Retrieve and follow the instructions at:
#  https://raw.githubusercontent.com/garrytan/gbrain/master/INSTALL_FOR_AGENTS.md"

# Or standalone:
git clone https://github.com/garrytan/gbrain.git && cd gbrain && bun install && bun link
gbrain init                     # local brain, ready in 2 seconds
gbrain import ~/notes/          # index your markdown
gbrain query "what themes show up across my notes?"
```

## MCP Server

```json
{
  "mcpServers": {
    "gbrain": { "command": "gbrain", "args": ["serve"] }
  }
}
```

Supports stdio, HTTP with OAuth 2.1, scoped operations, admin dashboard.

## Related Projects

- [GStack](https://github.com/garrytan/gstack) — Coding engine (70k+ stars), GBrain is the memory mod
- [OpenClaw](https://openclaw.ai) — Agent platform where GBrain runs in production
- [Hermes Agent](../sources/hermes_agent.md) — Self-improving agent compatible with GBrain

---

## Source

- [Raw Source](../../raw/gbrain_20260512.md)
- [GitHub Repository](https://github.com/garrytan/gbrain)
- [GBrain Evals](https://github.com/garrytan/gbrain-evals)

## Related Topics

- [Personal Agents](../topics/personal_agent.md) — Agent Sources section
- [Building Agent Apps](../topics/building_agent_apps.md) — Agent Memory section
- [Agent Skills](../topics/agent_skills.md) — Skill evolution systems

## Related Entities

- [Garry Tan](../entities/garrytan.md)
- [Nous Research](../entities/nous_research.md) — Hermes Agent
