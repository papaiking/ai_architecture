---
title: "Deep Agents"
type: "source"
category: "Builder_agents"
tags: ["agent", "framework", "langchain", "langgraph", "planning", "subagent"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["https://github.com/langchain-ai/deepagents"]
---

# Deep Agents

**Organization**: LangChain
**License**: MIT

## Overview

Python library giúp build AI agent kiểu "Claude Code / Deep Research" nhanh. Có sẵn planning, subagent, filesystem, memory và human-in-the-loop, xây trên LangChain + LangGraph.

## Installation

```bash
pip install deepagents
# hoặc: uv add deepagents / poetry add deepagents
```

## Core Capabilities

| Capability | Description |
|------------|------------|
| **Planning** | Tool write_todos để agent tự viết to-do list, chia nhỏ task |
| **Context Management** | Filesystem tools (ls, read_file, write_file, edit_file), auto-summarization |
| **Subagent Spawning** | Tool task spawn các subagent chuyên biệt |
| **Long-term Memory** | LangGraph Store / Memory Store |
| **Shell Execution** | Tool execute chạy lệnh trong sandbox |
| **Filesystem Permissions** | Rule giới hạn file/folder |
| **Human-in-the-loop** | Interrupt để xin approval trước khi chạy tool |

## Basic Usage

```python
from deepagents import create_deep_agent

def get_weather(city: str) -> str:
    return f"It's always sunny in {city}!"

agent = create_deep_agent(
    model="google_genai:gemini-3.1-pro-preview",
    tools=[get_weather],
    system_prompt="You are a helpful assistant",
)

agent.invoke({"messages": [{"role": "user", "content": "weather in sf"}]})
```

## Deep Research Example

```python
from tavily import TavilyClient
from deepagents import create_deep_agent

def internet_search(query: str, max_results: int = 5):
    client = TavilyClient(api_key=os.environ["TAVILY_API_KEY"])
    return client.search(query, max_results=max_results)

agent = create_deep_agent(
    tools=[internet_search],
    system_prompt="You are an expert researcher.",
)

result = agent.invoke({"messages": [{"role": "user", "content": "What is langgraph?"}]})
```

## Customization Options

- **Model**: Claude, OpenAI, Anthropic, Google, OpenRouter, Ollama...
- **System Prompt**: Viết prompt riêng theo use case
- **Tools**: Web search, internal API, DB...
- **Middleware**: TodoListMiddleware, FilesystemMiddleware, SubAgentMiddleware
- **Subagents**: Dict hoặc CompiledSubAgent
- **Memory**: InMemoryStore hoặc LangGraph store
- **Interrupt**: Define tool cần approval trước khi chạy

## Khi nào nên dùng?

- Task phức tạp nhiều bước, cần planning
- Context lớn: nhiều tài liệu, logs, kết quả RAG
- Cần filesystem backend linh hoạt
- Chạy code trong sandbox, delegate sang subagent
- Lưu memory dài hạn
- Kiểm soát quyền filesystem
- Thêm bước approve của người dùng

---

## Source

- [Wiki Source](../wiki/sources/deep_agents.md)
- [GitHub](https://github.com/langchain-ai/deepagents)