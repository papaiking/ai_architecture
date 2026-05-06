---
title: "Understand Anything"
type: "source"
tags: ["codebase", "knowledge-graph", "plugin", "claude-code", "research"]
created: "2026-04-30"
updated: "2026-04-30"
sources: ["raw/understand_anything_20260430.md"]
category: "Builder_agents"
---

# Understand Anything

Turn any codebase, knowledge base, or docs into an interactive knowledge graph you can explore, search, and ask questions about.

**GitHub**: [Lum1104/Understand-Anything](https://github.com/Lum1104/Understand-Anything)  
**License**: MIT  
**Homepage**: [understand-anything.com](https://understand-anything.com)  
**Live Demo**: [Demo](https://understand-anything.com/demo/)

![Understand Anything Dashboard](../media/understand-anything.png)

## Overview

Understand Anything is a [Claude Code Plugin](https://code.claude.com/docs/en/plugins-reference#plugins-reference) that analyzes your project with a multi-agent pipeline, builds a knowledge graph of every file, function, class, and dependency, then gives you an interactive dashboard to explore it all visually.

> **Graphs that teach > graphs that impress.**

## Key Features

### Explore the Structural Graph
Navigate your codebase as an interactive knowledge graph — every file, function, and class is a node you can click, search, and explore. Select any node to see plain-English summaries, relationships, and guided tours.

### Understand Business Logic
Switch to the domain view and see how your code maps to real business processes — domains, flows, and steps laid out as a horizontal graph.

### Analyze Knowledge Bases
Point `/understand-knowledge` at a [Karpathy-pattern LLM wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) and get a force-directed knowledge graph with community clustering. The deterministic parser extracts wikilinks and categories from `index.md`, then LLM agents discover implicit relationships, extract entities, and surface claims — turning your wiki into a navigable graph of interconnected ideas.

### Additional Features

- **Guided Tours**: Auto-generated walkthroughs of the architecture, ordered by dependency
- **Fuzzy & Semantic Search**: Find anything by name or by meaning
- **Diff Impact Analysis**: See which parts of the system your changes affect before you commit
- **Persona-Adaptive UI**: Dashboard adjusts detail level based on who you are — junior dev, PM, or power user
- **Layer Visualization**: Automatic grouping by architectural layer (API, Service, Data, UI, Utility)
- **Language Concepts**: 12 programming patterns explained in context

## Multi-Agent Pipeline

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

File analyzers run in parallel (up to 5 concurrent, 20-30 files per batch). Supports incremental updates.

## Platform Compatibility

Works with Claude Code, Codex, OpenCode, OpenClaw, Cursor, VS Code + GitHub Copilot, Copilot CLI, Antigravity, Gemini CLI, Pi Agent.

## Share the Graph with Your Team

The graph is just JSON — **commit it once, and teammates skip the pipeline**. Good for onboarding, PR reviews, and docs-as-code.

**What to commit:** everything in `.understand-anything/` *except* `intermediate/` and `diff-overlay.json`.

## Commands

```bash
/understand                      # Analyze codebase
/understand-dashboard            # Explore the dashboard
/understand-chat                 # Ask anything about the codebase
/understand-diff                 # Analyze impact of changes
/understand-explain <file>       # Deep-dive into specific file
/understand-onboard              # Generate onboarding guide
/understand-domain               # Extract business domain knowledge
/understand-knowledge <path>     # Analyze LLM wiki knowledge base
```

## Nguồn

- [Understand Anything Raw Source](../../raw/understand_anything_20260430.md)

## Liên kết liên quan

- [AI Coding Agents](../topics/builder_agents.md) - Topic covering AI coding assistants
- [Research Agents](../topics/Research_agents.md) - Topic covering research agents
- [Builder Agents](../topics/builder_agents.md) - Building AI agents for coding
