---
title: "The Anatomy of an Agent Harness"
type: "source"
category: "Builder_agents"
tags: ["agent", "harness", "infrastructure", "anthropic", "openai", "langchain"]
created: "2026-04-20"
updated: "2026-04-20"
sources: ["https://www.dailydoseofds.com/p/the-anatomy-of-an-agent-harness/"]
---

# The Anatomy of an Agent Harness

**Author**: Avi Chawla
**Source**: Daily Dose of Data Science
**Date**: Apr 7, 2026

---

## Overview

Deep dive into what Anthropic, OpenAI, Perplexity and LangChain are actually building when they create "agents".

## Key Insight

> "If you're not the model, you're the harness."

The agent is the emergent behavior (goal-directed, tool-using, self-correcting). The harness is the machinery producing that behavior.

## The 11 Components of Production Harness

### 1. The Orchestration Loop
- Implements Thought-Action-Observation (TAO) / ReAct loop
- "Dumb loop" where all intelligence lives in the model

### 2. Tools
- Defined as schemas (name, description, parameters)
- Categories: file operations, search, execution, web access, code intelligence, subagent spawning

### 3. Memory
- **Short-term**: conversation history within session
- **Long-term**: cross-session persistence (CLAUDE.md, MEMORY.md, JSON Stores)
- Three-tier: lightweight index, detailed topic files, raw transcripts

### 4. Context Management
- Context rot: 30%+ performance degradation in mid-window positions
- Strategies: compaction, observation masking, just-in-time retrieval, sub-agent delegation

### 5. Prompt Construction
- Hierarchical: system prompt + tool definitions + memory + history + user message

### 6. Output Parsing
- Native tool calling returns structured tool_calls objects
- Schema-constrained responses via Pydantic models

### 7. State Management
- Typed dictionaries flowing through graph nodes
- Checkpointing at super-step boundaries

### 8. Error Handling
- 4 types: transient (retry), LLM-recoverable, user-fixable, unexpected
- 10-step process with 99% per-step = ~90.4% end-to-end

### 9. Guardrails and Safety
- Input guardrails, output guardrails, tool guardrails
- Permission enforcement separates from model reasoning

### 10. Verification Loops
- Rules-based (tests, linters), visual feedback, LLM-as-judge
- "Giving the model a way to verify its work improves quality by 2 to 3x"

### 11. Subagent Orchestration
- Fork, Teammate, Worktree models
- Agents-as-tools, handoffs, nested state graphs

## Frameworks

- **Anthropic Claude Agent SDK**: Gather-Act-Verify cycle, "dumb loop"
- **OpenAI Agents SDK**: Runner class with async/sync/streamed modes, code-first
- **LangGraph**: Explicit state graph with llm_call and tool_node nodes
- **CrewAI**: Role-based multi-agent (Agent, Task, Crew)

## Seven Design Decisions

1. Single-agent vs multi-agent
2. ReAct vs plan-and-execute
3. Context window management strategy
4. Verification loop design
5. Permission and safety architecture
6. Tool scoping strategy
7. Harness thickness (how much logic in harness vs model)

## Key Takeaways

- The harness is not a commodity layer - it's where the hard engineering lives
- Two products with identical models can have wildly different performance
- Field moving toward thinner harnesses as models improve
- Models are post-trained with specific harnesses (tight coupling)

---

## Related Topics

- [Builder Agents](../wiki/topics/builder_agents.md)
- [Agent Skills](../wiki/topics/agent_skills.md)

---

## Source

- [Article](https://www.dailydoseofds.com/p/the-anatomy-of-an-agent-harness/)