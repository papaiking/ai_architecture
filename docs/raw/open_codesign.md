# Open CoDesign - Open Source AI Design Tool

**Organization**: OpenCoworkAI
**Repository**: OpenCoworkAI/open-codesign

## Overview

Open CoDesign is an open-source desktop AI design tool that aims to be a local, subscription-free alternative to Claude Design, focused on generating and iterating on interactive UI prototypes and other design artifacts from natural language prompts.

## Purpose

An Electron-based desktop app that lets you use your own model/API keys (BYOK) to generate interactive prototypes, slides, marketing pages, and similar design outputs from prompts.

Positioned as an open-source, local Claude Design replacement with no subscriptions or hosted quota limits.

## Key Features

- **Multi-model support**: Built-in support for Anthropic Claude, OpenAI GPT, Google Gemini, DeepSeek, OpenRouter, SiliconFlow, local Ollama, and any OpenAI-compatible endpoint
- **BYOK (bring your own key)**: You paste your own API keys; the app does not ship with a hosted backend or embedded provider account
- **One-click config import**: Can read your existing Claude Code or Codex config (e.g. ~/.codex/config.toml, ~/.claude/settings.json) and import providers, models, and keys automatically
- **Local-first**: Configuration is stored under ~/.config/open-codesign/config.toml and encrypted with Electron safeStorage, with an explicit claim that no credentials are uploaded
- **Outputs**: Generates artifacts that render in a sandboxed iframe as either HTML or live React components, and supports export to HTML, PDF (via local Chrome), PPTX, ZIP, and Markdown on-device
- **Interaction**: Supports inline comments on elements in the preview (model rewrites only that region), tunable sliders for parameters like color/spacing/font, and quick switching between the last several designs kept "alive" for instant preview

## Architecture

From the quickstart and docs, you can build and run from source via:

```bash
git clone https://github.com/OpenCoworkAI/open-codesign.git
pnpm install
pnpm dev
```

This requires Node 22 LTS and pnpm 9.15+, and runs a typical Electron + web stack with a sandboxed preview iframe for rendered artifacts.

## Installation and Platforms

### macOS
```bash
brew install --cask opencoworkai/tap/open-codesign
```
Or download open-codesign-*-arm64.dmg / *-x64.dmg from GitHub Releases.

### Windows
```bash
scoop bucket add opencoworkai …
scoop install open-codesign
```
Or download *-x64-setup.exe / *-arm64-setup.exe.

### Linux
AppImage open-codesign-*-x64.AppImage from Releases.

Note: Current installers are marked as unsigned in v0.1.

## Typical Workflow

1. Install the app via package manager or direct download
2. On first launch, add a provider:
   - Import from Claude Code / Codex config, or
   - Manually paste an API key (provider auto-detected from prefix), or
   - Use keyless mode with an IP-allowlisted proxy or local Ollama
3. Open the Hub, pick one of the built-in demo prompts or type your own
4. The tool generates and renders an artifact inside a sandboxed iframe as HTML or React
5. Iterate via inline comments, sliders, or switching between recent designs, then export to your desired format

## Relation to Other OpenCowork Projects

Open CoDesign sits alongside open-cowork, which is an open-source Claude Cowork–style multi-agent desktop app by the same org. Together they aim to replicate the Claude Code/Cowork/Design ecosystem locally, with CoDesign focused specifically on visual and interactive design generation rather than coding or agent workflows.

---

**Source**: [GitHub](https://github.com/OpenCoworkAI/open-codesign)
**Date**: 2026-04-22