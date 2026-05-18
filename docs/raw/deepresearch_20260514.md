# Tongyi DeepResearch

**Org**: Alibaba-NLP (Tongyi Lab)
**GitHub**: https://github.com/Alibaba-NLP/DeepResearch
**License**: Apache 2.0
**Stars**: 18.9k
**Latest Release**: N/A (300 commits)
**Date**: 2026-05-14
**Paper**: https://arxiv.org/pdf/2510.24701

---

Tongyi DeepResearch is an agentic large language model featuring 30.5 billion total parameters, with only 3.3 billion activated per token (30B-A3B, 128K context). Developed by Tongyi Lab (Alibaba), specifically designed for **long-horizon, deep information-seeking** tasks.

State-of-the-art performance across agentic search benchmarks: Humanity's Last Exam, BrowseComp, BrowseComp-ZH, WebWalkerQA, xbench-DeepSearch, FRAMES, SimpleQA.

## Features

- **Fully automated synthetic data generation pipeline**: Highly scalable data synthesis pipeline, fully automatic, empowers agentic pre-training, supervised fine-tuning, and reinforcement learning.
- **Large-scale continual pre-training on agentic data**: Diverse, high-quality agentic interaction data to extend model capabilities, maintain freshness, strengthen reasoning.
- **End-to-end reinforcement learning**: Strictly on-policy RL based on customized Group Relative Policy Optimization (GRPO) framework, with token-level policy gradients, leave-one-out advantage estimation, selective filtering of negative samples.
- **Agent Inference Paradigm Compatibility**: Two inference paradigms — ReAct (core intrinsic abilities) and IterResearch-based "Heavy" mode (test-time scaling for maximum performance ceiling).

## Model

| Model | Size | Context |
|-------|------|---------|
| Tongyi-DeepResearch-30B-A3B | 30B-A3B | 128K |

Available on HuggingFace, ModelScope, OpenRouter.

## Deep Research Agent Family

Extensive research family including WebWalker (ACL 2025), WebDancer (NeurIPS 2025), WebSailor, WebShaper, WebWatcher, WebResearcher, ReSum, WebWeaver, WebSailor-V2, AgentFold, WebLeaper, BrowseConf, ParallelMuse, AgentFrontier, and more.

## Quick Start

- Python 3.10.0, Conda environment
- Dependencies: Serper.dev (web search), Jina.ai (page reading), OpenAI-compatible API (summarization), Dashscope (file parsing), SandboxFusion (Python sandbox)
- Two input formats: JSONL and JSON
- ReAct or IterResearch inference via run_react_infer.sh
- OpenRouter API for GPU-free inference
