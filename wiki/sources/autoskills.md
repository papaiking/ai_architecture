---
title: "Autoskills"
type: "source"
category: "Builder_agents"
tags: ["skills", "automation", "cli", "tooling", "builder-agent"]
created: "2026-04-18"
updated: "2026-04-19"
related_topics: ["topics/builder_agents.md"]
entities: ["midudev.md"]
---

# Autoskills

**Type**: CLI Tool

One command. Your entire AI skill stack. Installed.

[autoskills.sh](https://autoskills.sh) | [GitHub](https://github.com/midudev/autoskills)

## Overview

Autoskills is a CLI tool that automatically installs the best AI agent skills for your project. It scans your project files (package.json, Gradle, config files), detects your tech stack, and installs matching AI agent skills from skills.sh automatically.

## Details

- **Org**: midudev
- **Stars**: 3.4k
- **Forks**: 336
- **License**: CC BY-NC 4.0
- **Releases**: 12 (latest: v0.2.7)
- **Commits**: 231
- **Language**: TypeScript (72%), JavaScript (14.5%), Astro (10.5%)

## How It Works

1. Run `npx autoskills` in your project root
2. Your `package.json`, Gradle files, and config files are scanned to detect technologies
3. The best matching AI agent skills are installed via skills.sh
4. If Claude Code is targeted, a CLAUDE.md summary is generated

## Options

```
-y, --yes       Skip confirmation prompt
--dry-run       Show what would be installed without installing
-h, --help      Show help message
```

## Usage

```bash
# Basic usage (scans project and installs skills)
npx autoskills

# Skip confirmation prompt
npx autoskills --yes

# Preview what would be installed
npx autoskills --dry-run

# Generate CLAUDE.md for Claude Code
npx autoskills -a
# or
npx autoskills --claude-code
```

## Supported Technologies

### Frameworks & UI
React, Next.js, Vue, Nuxt, Svelte, Angular, Astro, Tailwind CSS, shadcn/ui, GSAP, Three.js

### Languages & Runtimes
TypeScript, Node.js, Go, Bun, Deno, Dart

### Backend & APIs
Express, Hono, NestJS, Spring Boot

### Mobile & Desktop
Expo, React Native, Flutter, SwiftUI, Android, Kotlin Multiplatform, Tauri, Electron

### Data & Storage
Supabase, Neon, Prisma, Drizzle ORM, Zod, React Hook Form

### Auth & Billing
Better Auth, Clerk, Stripe

### Testing
Vitest, Playwright

### Cloud & Infrastructure
Vercel, Vercel AI SDK, Cloudflare, Durable Objects, Cloudflare Agents, Cloudflare AI, AWS, Azure, Terraform

### Tooling
Turborepo, Vite, oxlint

### Media & AI
Remotion, ElevenLabs

## Requirements

- Node.js >= 22

## Related Projects

- [skills.sh](https://skills.sh) - AI agent skills marketplace
- [Claude Code](https://claude.com/claude-code) - AI coding assistant

---

## Nguồn

- [GitHub Repository](https://github.com/midudev/autoskills)

## Liên kết liên quan

- [Builder Agents](../topics/builder_agents.md)
- [midudev](../entities/midudev.md)