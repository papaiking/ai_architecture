---
title: "Personal AI Infrastructure (PAI) — v5.0.0"
type: "source"
category: "Personal_agents"
tags: ["life-os", "claude-code", "digital-assistant", "pulse", "personal-agent"]
created: "2026-05-14"
updated: "2026-05-14"
sources: ["raw/personal_ai_infrastructure_20260514.md"]
---

# Personal AI Infrastructure (PAI) — v5.0.0

- **Source:** [github.com/danielmiessler/Personal_AI_Infrastructure](https://github.com/danielmiessler/Personal_AI_Infrastructure)
- **Author:** [Daniel Miessler](https://danielmiessler.com)
- **License:** MIT

---

PAI is a **Life Operating System** built on Claude Code — capturing who you are, what you care about, and where you're going, and helping you get there with AI that knows you.

![PAI Logo](../media/pai_logo.png)

## Architecture — Three Layers

| Layer | Role |
|-------|------|
| **PAI** | The OS — skills, memory, Algorithm, Telos, identity files |
| **Pulse** | Life Dashboard at `localhost:31337` — state, goals, work |
| **The DA** | Digital Assistant — voice and personality |

## Key Concepts

- **Ideal State** — current → ideal state transition drives everything
- **ISA (Ideal State Artifact)** — 12-section document (Problem → Vision → Criteria → Verification)
- **Algorithm v6.3.0** — 7-phase loop: OBSERVE → THINK → PLAN → BUILD → EXECUTE → VERIFY → LEARN
- **Memory v7.6** — structured by purpose: WORK, KNOWLEDGE, LEARNING, RELATIONSHIP, OBSERVABILITY, STATE
- **Containment zones** — structural privacy with 12 security gates
- **Text-first, no RAG** — filesystem as context, ripgrep for search

## Features (v5.0.0)

- **Pulse daemon** — unified service: voice, hooks, cron, Life Dashboard (22 routes), wiki API, Telegram/iMessage bridges
- **The DA identity** — PRINCIPAL_IDENTITY + DA_IDENTITY, `/interview` wizard for setup
- **45 skills** — self-activating composable domain units
- **171 workflows** — deterministic execution pipelines
- **37 hooks** — SessionStart, UserPromptSubmit, PreToolUse, PostToolUse, etc.
- **One-line installer** — `curl -sSL https://ourpai.ai/install.sh | bash`

## Installation

```bash
curl -sSL https://ourpai.ai/install.sh | bash
```

After install: `open http://localhost:31337` for the Life Dashboard, then run `/interview` in Claude Code.

## Nguồn

- [Raw Source](../../raw/personal_ai_infrastructure_20260514.md)

## Liên kết liên quan

- [Daniel Miessler](../entities/daniel_miessler.md) — Creator of PAI and fabric
- [GBrain](./gbrain.md) — AI agent memory & knowledge system
- [Obsidian](./obsidian.md) — Markdown second brain
- [QwenPaw](./qwenpaw.md) — Personal AI assistant
- [Personal Agents](../topics/personal_agent.md) — Personal agent applications
