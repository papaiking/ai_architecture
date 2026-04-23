# Crucix - Personal Intelligence Agent

**Organization**: calesthio
**Repository**: calesthio/Crucix
**License**: MIT

## Overview

Crucix is a self-hosted, open-source "personal intelligence agent" that watches many real-time data sources and alerts you when something important changes.

It is an intelligence dashboard that aggregates dozens of live feeds (OSINT-style), such as satellite fire detection, flight tracking, radiation monitoring, conflict events, economic indicators, and social sentiment, into a single HUD-like interface.

The goal is to run it on your own infrastructure (Docker), customize the sources you care about, and get notifications when signals cross certain thresholds or when notable events happen.

## Main Capabilities

- **Data aggregation**: Connects to about 26-27 different data sources; some are public feeds, others require API keys that you place in an .env file
- **Real-time monitoring**: Continuously polls or streams data and updates a central dashboard where you can visually track global events, markets, and risks
- **Alerting / pings**: When certain conditions or anomalies are detected, it can ping you through configured channels
- **Optional LLM layer**: Large-language-model component that can turn the collected narratives into trading ideas or summaries and can interact with you via Telegram or Discord

## Tech Stack

- **Backend**: Node.js, minimal dependencies for self-hosting
- **Frontend**: Modern web UI (Tailwind + shadcn/ui, dark theme)
- **Deployment**: Docker-based

## Typical Usage

```bash
git clone https://github.com/calesthio/Crucix.git
cd Crucix
cp .env.example .env  # fill in your API keys
docker compose up -d
```

## Use Cases

- **OSINT and security enthusiasts**: Track conflicts, disasters, and infrastructure events
- **Traders and macro watchers**: Combine news, economic indicators, and sentiment to inform decisions
- **Researchers and hobbyists**: Personal "world monitor" that is private and customizable

---

**Source**: [GitHub](https://github.com/calesthio/Crucix)
**Date**: 2026-04-22