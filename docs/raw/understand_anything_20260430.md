# Understand Anything

**Turn any codebase, knowledge base, or docs into an interactive knowledge graph you can explore, search, and ask questions about.**

Works with Claude Code, Codex, Cursor, Copilot, Gemini CLI, and more.

## Overview

You just joined a new team. The codebase is 200,000 lines of code. Where do you even start?

Understand Anything is a [Claude Code Plugin](https://code.claude.com/docs/en/plugins-reference#plugins-reference) that analyzes your project with a multi-agent pipeline, builds a knowledge graph of every file, function, class, and dependency, then gives you an interactive dashboard to explore it all visually. Stop reading code blind. Start seeing the big picture.

**Graphs that teach > graphs that impress.**

## Features

### Explore the structural graph

Navigate your codebase as an interactive knowledge graph — every file, function, and class is a node you can click, search, and explore. Select any node to see plain-English summaries, relationships, and guided tours.

### Understand business logic

Switch to the domain view and see how your code maps to real business processes — domains, flows, and steps laid out as a horizontal graph.

### Analyze knowledge bases

Point `/understand-knowledge` at a [Karpathy-pattern LLM wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) and get a force-directed knowledge graph with community clustering. The deterministic parser extracts wikilinks and categories from `index.md`, then LLM agents discover implicit relationships, extract entities, and surface claims — turning your wiki into a navigable graph of interconnected ideas.

### Additional Features

- **Guided Tours**: Auto-generated walkthroughs of the architecture, ordered by dependency. Learn the codebase in the right order.
- **Fuzzy & Semantic Search**: Find anything by name or by meaning. Search "which parts handle auth?" and get relevant results across the graph.
- **Diff Impact Analysis**: See which parts of the system your changes affect before you commit. Understand ripple effects across the codebase.
- **Persona-Adaptive UI**: The dashboard adjusts its detail level based on who you are — junior dev, PM, or power user.
- **Layer Visualization**: Automatic grouping by architectural layer — API, Service, Data, UI, Utility — with color-coded legend.
- **Language Concepts**: 12 programming patterns (generics, closures, decorators, etc.) explained in context wherever they appear.

## Quick Start

### 1. Install the plugin

```bash
/plugin marketplace add Lum1104/Understand-Anything
/plugin install understand-anything
```

### 2. Analyze your codebase

```bash
/understand
```

A multi-agent pipeline scans your project, extracts every file, function, class, and dependency, then builds a knowledge graph saved to `.understand-anything/knowledge-graph.json`.

### 3. Explore the dashboard

```bash
/understand-dashboard
```

An interactive web dashboard opens with your codebase visualized as a graph — color-coded by architectural layer, searchable, and clickable. Select any node to see its code, relationships, and a plain-English explanation.

### 4. Keep learning

```bash
# Ask anything about the codebase
/understand-chat How does the payment flow work?

# Analyze impact of your current changes
/understand-diff

# Deep-dive into a specific file or function
/understand-explain src/auth/login.ts

# Generate an onboarding guide for new team members
/understand-onboard

# Extract business domain knowledge (domains, flows, steps)
/understand-domain

# Analyze a Karpathy-pattern LLM wiki knowledge base
/understand-knowledge ~/path/to/wiki
```

## Multi-Platform Installation

Understand-Anything works across multiple AI coding platforms.

### Claude Code (Native)

```bash
/plugin marketplace add Lum1104/Understand-Anything
/plugin install understand-anything
```

### Codex

Tell Codex:
```
Fetch and follow instructions from https://raw.githubusercontent.com/Lum1104/Understand-Anything/refs/heads/main/.codex/INSTALL.md
```

### OpenCode

Tell OpenCode:
```
Fetch and follow instructions from https://raw.githubusercontent.com/Lum1104/Understand-Anything/refs/heads/main/.opencode/INSTALL.md
```

### Cursor

Cursor auto-discovers the plugin via `.cursor-plugin/plugin.json` when this repo is cloned. No manual installation needed — just clone and open in Cursor.

### VS Code + GitHub Copilot

VS Code with GitHub Copilot (v1.108+) auto-discovers the plugin via `.copilot-plugin/plugin.json` when this repo is cloned. No manual installation needed — just clone and open in VS Code.

### Other Platforms

Also supports: OpenClaw, Copilot CLI, Antigravity, Gemini CLI, Pi Agent.

## Share the Graph with Your Team

The graph is just JSON — **commit it once, and teammates skip the pipeline**. Good for onboarding, PR reviews, and docs-as-code.

**What to commit:** everything in `.understand-anything/` *except* `intermediate/` and `diff-overlay.json` (those are local scratch).

Large graphs (10 MB+) can be tracked with **git-lfs**.

## Under the Hood

### Multi-Agent Pipeline

The `/understand` command orchestrates 5 specialized agents, and `/understand-domain` adds a 6th:

| Agent | Role |
|-------|------|
| `project-scanner` | Discover files, detect languages and frameworks |
| `file-analyzer` | Extract functions, classes, imports; produce graph nodes and edges |
| `architecture-analyzer` | Identify architectural layers |
| `tour-builder` | Generate guided learning tours |
| `graph-reviewer` | Validate graph completeness and referential integrity |
| `domain-analyzer` | Extract business domains, flows, and process steps |
| `article-analyzer` | Extract entities, claims, and implicit relationships from wiki articles |

File analyzers run in parallel (up to 5 concurrent, 20-30 files per batch). Supports incremental updates — only re-analyzes files that changed since the last run.

## Links

- **GitHub**: https://github.com/Lum1104/Understand-Anything
- **Homepage**: https://understand-anything.com
- **Live Demo**: https://understand-anything.com/demo/
- **Discord**: https://discord.gg/pydat66RY
- **License**: MIT
