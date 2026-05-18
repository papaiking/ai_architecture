---
title: "Crucix"
type: "source"
category: "AI_applications"
tags: ["intelligence", "monitoring", "osint", "real-time", "alerts", "dashboard"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["raw/crucix.md"]
related_topics: ["topics/ai_applications.md"]
---

# Crucix - Personal Intelligence Agent

- **Organization**: calesthio
- **Repository**: calesthio/Crucix
- **License**: MIT

## Overview

Crucix is a self-hosted, open-source "personal intelligence agent" that watches many real-time data sources and alerts you when something important changes.

An intelligence dashboard aggregating dozens of live feeds (OSINT-style) into a single HUD-like interface.

## Key Features

- **Data aggregation**: ~26-27 different data sources (public feeds + API key required)
- **Real-time monitoring**: Continuously polls/streams data to central dashboard
- **Alerting**: Ping through configured channels when conditions met
- **Optional LLM layer**: Transform narratives into trading ideas, interact via Telegram/Discord

## Tech Stack

- **Backend**: Node.js
- **Frontend**: Tailwind + shadcn/ui
- **Deployment**: Docker

## Quick Start

```bash
git clone https://github.com/calesthio/Crucix.git
cd Crucix
cp .env.example .env
docker compose up -d
```

## Use Cases

- OSINT and security tracking (conflicts, disasters, infrastructure)
- Traders/macro watchers (news + economic indicators)
- Research hobbyists (personal world monitor)

## Related Topics

- [AI Applications](../topics/ai_applications.md)

---

## Source

- [Raw Source](../../raw/crucix.md)
- [GitHub](https://github.com/calesthio/Crucix)