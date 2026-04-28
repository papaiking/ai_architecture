# code-review-graph

**Organization**: tirth8205
**Stars**: 13,307
**License**: MIT
**Website**: https://code-review-graph.com

## Overview

Local knowledge graph for Claude Code. Builds a persistent map of your codebase so Claude reads only what matters — 6.8× fewer tokens on reviews and up to 49× on daily coding tasks.

## Key Features

- **Structural map**: Builds a map of your code with Tree-sitter
- **Incremental tracking**: Tracks changes incrementally
- **MCP integration**: Gives your AI assistant precise context via MCP
- **Token efficiency**: 6.8× fewer tokens on reviews, 49× fewer on daily coding tasks

## Supported Languages

Python, TypeScript, JavaScript, and more

## Installation

```bash
pip install code-review-graph
code-review-graph install
code-review-graph build
```

## Architecture

- `parser.py` - Tree-sitter multi-language parser
- `graph.py` - SQLite graph store
- `tools.py` - MCP tool implementations
- `incremental.py` - Git diff + file watch logic
- `embeddings.py` - Vector embedding support
- `visualization.py` - D3.js HTML generator

---

**Source**: [GitHub](https://github.com/tirth8205/code-review-graph)
**Date**: 2026-04-22