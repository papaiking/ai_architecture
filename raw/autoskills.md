# Autoskills

## Overview

Autoskills is a CLI tool that automatically installs the best AI agent skills for your project. It scans your project files (package.json, Gradle, config files), detects your tech stack, and installs matching AI agent skills from skills.sh automatically.

## Details

- Org: midudev
- Stars: 3.3k
- License: CC BY-NC 4.0
- Releases: 12
- Language: TypeScript (72%), JavaScript (14.5%), Astro (10.5%)

## Key Features

- Auto-detects tech stack from project files
- Installs matching AI agent skills from skills.sh
- Generates CLAUDE.md summary for Claude Code projects
- No manual configuration needed
- Supports 50+ technologies across frontend, backend, mobile, cloud
- Skip confirmation with --yes flag
- Dry-run mode to preview installations

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
- [midudev](https://midu.dev) - Creator/author

---
*Accessed: 2026-04-18*