---
title: "Mirage - Unified Virtual Filesystem for AI Agents"
type: "source"
category: "Building_AI_applications"
tags: ["mcp", "vfs", "agent-framework", "sandbox", "filesystem"]
created: "2026-05-14"
updated: "2026-05-14"
sources: ["raw/mirage_20260514.md"]
---

# Mirage: A Unified Virtual File System for AI Agents

- **Source:** [github.com/strukto-ai/mirage](https://github.com/strukto-ai/mirage)
- **Author:** [strukto.ai](https://www.strukto.ai)
- **Stars:** 2.2k | **License:** Apache-2.0

---

Mirage is a **Unified Virtual Filesystem for AI Agents**: a single tree that mounts services and data sources (S3, GDrive, Slack, Gmail, Redis, etc.) side-by-side as one filesystem. Agents reach every backend with familiar Unix-like tools — zero new vocabulary needed.

![Mirage Logo](../media/mirage_logo.png)

## Key Features

- **One filesystem, every backend** — agents reason about one abstraction instead of N SDKs and M MCPs
- **Multiple resources mounted under a single root:** RAM, Disk, Redis, S3/R2/OCI/Supabase/GCS, Gmail/GDrive/GDocs/GSheets/GSlides, GitHub/Linear/Notion/Trello, Slack/Discord/Telegram/Email, MongoDB, SSH
- **Familiar bash tools** across every mount (ls, cat, grep, cp, find, etc.)
- **Portable workspaces** — clone, snapshot, and version environments
- **Python + TypeScript SDKs** — embed in FastAPI, Express, browser apps
- **Agent framework integrations:** OpenAI Agents SDK, Vercel AI SDK, LangChain, Pydantic AI, CAMEL, OpenHands
- **CLI + daemon** — plugs into Claude Code and Codex

## Architecture

![Mirage Architecture](../media/mirage_arch.svg)

The flow: AI Agent/Application → Mirage Bash & VFS → Dispatcher & Cache → Infrastructure & Remote services.

## Cache System

Two-layer cache for performance:
- **Index cache** — listings/metadata with TTL
- **File cache** — object bytes
- Pluggable backends: RAM (default, 512 MB) or Redis (shared across workers)

## Nguồn

- [Raw Source](../../raw/mirage_20260514.md)

## Liên kết liên quan

- [Pipecat](./pipecat.md) — Voice & multimodal AI framework
- [BlueRock](./bluerock.md) — MCP security sensor
- [Agent Harness](./agent_harness.md) — Agent infrastructure patterns
- [Building Agent Apps](../topics/building_agent_apps.md) — Agent application engineering
