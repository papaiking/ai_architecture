---
title: "Deep Agents"
type: "source"
category: "Builder_agents"
tags: ["agent", "framework", "langchain", "langgraph", "planning", "subagent"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["raw/deep_agents.md"]
related_topics: ["topics/builder_agents.md"]
---

# Deep Agents

**Organization**: LangChain

## Overview

Python library giúp build AI agent kiểu "Claude Code / Deep Research" nhanh. Xây trên LangChain + LangGraph với planning, subagent, filesystem, memory và human-in-the-loop.

## Key Features

- **Planning**: write_todos tool cho task decomposition
- **Context Management**: Filesystem tools + auto-summarization
- **Subagent Spawning**: Task tool để spawn subagent
- **Long-term Memory**: LangGraph Store
- **Shell Execution**: Run commands trong sandbox
- **Human-in-the-loop**: Interrupt để xin approval

## Installation

```bash
pip install deepagents
```

## Usage

```python
from deepagents import create_deep_agent

agent = create_deep_agent(
    model="claude",
    tools=[...],
    system_prompt="You are a helpful assistant",
)
```

## Khi nào dùng?

- Task phức tạp cần planning
- Context lớn, cần đẩy ra filesystem
- Cần subagent, memory dài hạn
- Human approval cho tool nhạy cảm

---

## Related Topics

- [Builder Agents](../topics/builder_agents.md)

---

## Source

- [Raw Source](../../raw/deep_agents.md)
- [GitHub](https://github.com/langchain-ai/deepagents)