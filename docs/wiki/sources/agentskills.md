---
title: "Agent Skills"
type: "source"
category: "Builder_agents"
tags: ["agent-skills", "skills", "open-standard", "anthropic", "extensibility", "SKILL.md"]
created: "2026-05-15"
updated: "2026-05-15"
related_topics: ["topics/agent_skills.md"]
sources: ["raw/agentskills_20260515.md"]
---

# Agent Skills — Open Standard

- **Source:** [agentskills.io](https://agentskills.io)
- **GitHub:** [github.com/agentskills/agentskills](https://github.com/agentskills/agentskills)
- **Org:** Anthropic (original creator), open standard

A lightweight, open format for extending AI agent capabilities with specialized knowledge and workflows. Adopted by Claude Code, GitHub Copilot, Cursor, OpenAI Codex, Gemini CLI, and 30+ other agent products.

[Website](https://agentskills.io) | [Specification](https://agentskills.io/specification) | [GitHub](https://github.com/agentskills/agentskills) | [Discord](https://discord.gg/MKPE9g8aUy)

## Overview

Agent Skills is the open standard for packaging procedural knowledge into portable `SKILL.md` files that agents load on demand. Originally developed by Anthropic, it uses a progressive disclosure model: agents discover skills by name/description (~100 tokens), activate the full instructions when relevant (< 5000 tokens), and load scripts/references only as needed.

## Key Features

- **Open Format** — Simple directory structure with `SKILL.md` + optional scripts/references/assets
- **Progressive Disclosure** — Minimal context footprint; full instructions load only when needed
- **Cross-Product** — Build once, use across 30+ compatible agents
- **Validation** — `skills-ref` CLI tool for frontmatter and naming validation
- **Community** — Open standard with contributions from the broader ecosystem

## Specification Highlights

- `name`: 1-64 chars, lowercase + hyphens
- `description`: 1-1024 chars, what + when to use
- Optional: `license`, `compatibility`, `metadata`, `allowed-tools`
- Scripts in Python, Bash, JavaScript

## Ecosystem

Adopted by: Claude Code, Claude AI, GitHub Copilot, VS Code, OpenAI Codex, Gemini CLI, Cursor, OpenCode, OpenHands, Goose, JetBrains Junie, Roo Code, Factory, Coder Mux, Amp, Letta, and more.

## Nguồn

- [Raw Source](../../raw/agentskills_20260515.md)
- [Agent Skills Website](https://agentskills.io)
- [Specification](https://agentskills.io/specification)

## Liên kết liên quan

- [Agent Skills Topic](../topics/agent_skills.md)
- [SkillClaw](../sources/skillclaw.md) — Skill evolution system
