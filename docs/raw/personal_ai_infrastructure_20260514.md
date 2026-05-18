# Personal AI Infrastructure (PAI) — v5.0.0

- **Source:** https://github.com/danielmiessler/Personal_AI_Infrastructure
- **Author:** Daniel Miessler
- **License:** MIT
- **Stars:** Active project by creator of fabric
- **Fetched:** May 14, 2026

---

PAI is a **Life Operating System** built on Claude Code. It captures who you are, what you care about, and where you're trying to go — and helps you get there using AI that knows you.

## Architecture (3 layers)

- **PAI** — the OS itself: Skills, memory, the Algorithm, Telos, identity files
- **Pulse** — Life Dashboard at localhost:31337
- **The DA** — Digital Assistant: voice and personality

## Principles

- Humans first, tech second
- Ideal State drives everything (current state → ideal state transition)
- Text over opaque storage (Markdown, avoid SQLite/Postgres)
- Context scaffolding > model quality
- Filesystem as context, no RAG
- Memory that compounds (3 tiers: WORK, KNOWLEDGE, LEARNING)
- Self-improvement loop
- Skills as deterministic units (code → CLI → workflows → SKILL.md)
- Thinking skills library (first principles, council debates, red team, etc.)

## Key Features (v5.0.0 — Life Operating System)

- **Pulse** — unified daemon (port 31337): voice, hooks, observability, cron, Life Dashboard (22 routes), wiki API
- **The DA** — Digital Assistant identity layer with PRINCIPAL_IDENTITY + DA_IDENTITY
- **Algorithm v6.3.0** — seven-phase loop: OBSERVE → THINK → PLAN → BUILD → EXECUTE → VERIFY → LEARN
- **ISA** — Ideal State Artifact: 12 sections, 5 identities, owned by ISA skill
- **Containment zones** — structural privacy with 12 security gates
- **Memory v7.6** — WORK, KNOWLEDGE, LEARNING, RELATIONSHIP, OBSERVABILITY, STATE
- **45 skills, 171 workflows, 37 hooks**

## Installation

```bash
curl -sSL https://ourpai.ai/install.sh | bash
```

## Related

- Creator also built [fabric](https://github.com/danielmiessler/fabric) — AI prompt patterns
