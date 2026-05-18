---
title: "Open CoDesign"
type: "source"
category: "Personal_agents"
tags: ["ai", "design", "desktop", "electron", "ui", "prototyping", "byok"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["raw/open_codesign.md"]
related_topics: ["topics/personal_agent.md", "topics/ai_applications.md"]
---

# Open CoDesign

- **Organization**: OpenCoworkAI
- **Repository**: OpenCoworkAI/open-codesign

## Overview

Open CoDesign is an open-source desktop AI design tool that aims to be a local, subscription-free alternative to Claude Design, focused on generating and iterating on interactive UI prototypes and other design artifacts from natural language prompts.

## Key Features

- **Multi-model support**: Anthropic Claude, OpenAI GPT, Google Gemini, DeepSeek, OpenRouter, SiliconFlow, local Ollama, any OpenAI-compatible endpoint
- **BYOK (bring your own key)**: Paste your own API keys; no hosted backend
- **One-click config import**: Import from Claude Code or Codex config
- **Local-first**: Config stored under ~/.config/open-codesign/config.toml, encrypted with Electron safeStorage
- **Outputs**: HTML, live React components, export to HTML/PDF/PPTX/ZIP/Markdown
- **Interaction**: Inline comments, tunable sliders, quick switching between designs

## Architecture

```bash
git clone https://github.com/OpenCoworkAI/open-codesign.git
pnpm install
pnpm dev
```

Requires Node 22 LTS and pnpm 9.15+.

## Installation

| Platform | Command |
|----------|---------|
| macOS | `brew install --cask opencoworkai/tap/open-codesign` |
| Windows | `scoop bucket add opencoworkai …; scoop install open-codesign` |
| Linux | AppImage from Releases |

## Typical Workflow

1. Install app
2. Add provider (import from Claude Code/Codex or paste API key)
3. Open Hub, pick demo prompt or type own
4. Generate artifact → render in sandboxed iframe
5. Iterate via comments/sliders → export

## Related Topics

- [Personal Agents](../topics/personal_agent.md)
- [AI Applications](../topics/ai_applications.md)

---

## Source

- [Raw Source](../../raw/open_codesign.md)
- [GitHub](https://github.com/OpenCoworkAI/open-codesign)