# PageIndex: Vectorless, Reasoning-based RAG

**Homepage**: [vectify.ai/pageindex](https://vectify.ai/pageindex)  
**Chat Platform**: [chat.pageindex.ai](https://chat.pageindex.ai)  
**Developer**: [pageindex.ai/developer](https://pageindex.ai/developer)  
**GitHub**: [github.com/VectifyAI/PageIndex](https://github.com/VectifyAI/PageIndex)  

## 📢 Updates

- **Agentic Vectorless RAG** — A simple agentic, vectorless RAG example with self-hosted PageIndex, using OpenAI Agents SDK
- **Scale PageIndex to Millions of Documents** — PageIndex File System is a file-level tree layer that lets PageIndex reason over an entire corpus
- **PageIndex Chat** — Human-like document analysis agent platform for professional long documents, available via MCP or API
- **PageIndex Framework** — Deep dive into PageIndex: an agentic, in-context tree index that enables LLMs to perform reasoning-based, human-like retrieval over long documents

## Introduction to PageIndex

Are you frustrated with vector database retrieval accuracy for long professional documents? Traditional vector-based RAG relies on semantic *similarity* rather than true *relevance*. But **similarity ≠ relevance** — what we truly need in retrieval is **relevance**, and that requires **reasoning**.

PageIndex is a **vectorless**, **reasoning-based RAG** system that builds a **hierarchical tree index** from long documents and uses LLMs to **reason** over that index for **agentic, context-aware retrieval**.

It simulates how *human experts* navigate and extract knowledge from complex documents through *tree search*, enabling LLMs to *think* and *reason* their way to the most relevant document sections.

### Core Features

- **No Vector DB**: Uses document structure and LLM reasoning for retrieval, instead of vector similarity search
- **No Chunking**: Documents are organized into natural sections, not artificial chunks
- **Human-like Retrieval**: Simulates how human experts navigate complex documents
- **Better Explainability and Traceability**: Retrieval is based on reasoning — traceable and interpretable, with page and section references

PageIndex achieved **state-of-the-art 98.7% accuracy** on FinanceBench, outperforming vector-based RAG solutions in professional document analysis.

## PageIndex Tree Structure

PageIndex transforms lengthy PDF documents into a semantic **tree structure**, similar to a "table of contents" but optimized for LLMs. Ideal for: financial reports, regulatory filings, academic textbooks, legal or technical manuals.

Example tree structure:

```json
{
  "title": "Financial Stability",
  "node_id": "0006",
  "start_index": 21,
  "end_index": 22,
  "summary": "The Federal Reserve ...",
  "nodes": [
    {
      "title": "Monitoring Financial Vulnerabilities",
      "node_id": "0007",
      "start_index": 22,
      "end_index": 28,
      "summary": "The Federal Reserve's monitoring ..."
    }
  ]
}
```

## Package Usage

### 1. Install dependencies

```bash
pip install --upgrade -r requirements.txt
```

### 2. Set LLM API key

Create a `.env` file with your LLM API key (supports multiple LLMs via LiteLLM):

```
OPENAI_API_KEY=your_openai_key_here
```

### 3. Generate PageIndex structure

```bash
python run_pageindex.py --pdf_path /path/to/your/document.pdf
```

Optional parameters:
- `--model`: LLM model (default: gpt-4o-2024-11-20)
- `--toc-check-pages`: Pages to check for table of contents (default: 20)
- `--max-pages-per-node`: Max pages per node (default: 10)
- `--max-tokens-per-node`: Max tokens per node (default: 20000)

### Markdown support

```bash
python run_pageindex.py --md_path /path/to/your/document.md
```

## Agentic Vectorless RAG

For a simple, end-to-end agentic vectorless RAG example using PageIndex with OpenAI Agents SDK:

```bash
pip install openai-agents
python examples/agentic_vectorless_rag_demo.py
```

## Case Study: Finance QA Benchmark

Mafin 2.5 is a reasoning-based RAG system for financial document analysis, powered by **PageIndex**. It achieved **98.7% accuracy** on the FinanceBench benchmark, significantly outperforming traditional vector-based RAG systems.

## Resources

- **Blog**: [pageindex.ai/blog](https://pageindex.ai/blog)
- **Developer**: [pageindex.ai/developer](https://pageindex.ai/developer) (MCP, API docs)
- **Cookbooks**: [docs.pageindex.ai/cookbook](https://docs.pageindex.ai/cookbook)
- **Tutorials**: [docs.pageindex.ai/tutorials](https://docs.pageindex.ai/tutorials)

## Citation

```
Mingtian Zhang, Yu Tang and PageIndex Team,
"PageIndex: Next-Generation Vectorless, Reasoning-based RAG",
PageIndex Blog, Sep 2025.
```
