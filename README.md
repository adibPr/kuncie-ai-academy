# Kuncie AI Academy — LLM Bootcamp

Learning material for the **Kuncie AI Academy Bootcamp (Tier 3: The Builders)**. A hands-on workshop series covering LangChain integration, RAG pipelines, security guardrails, and production evaluation.

## What's Inside

**4 Jupyter Notebooks:**

| Notebook | Topic |
|---|---|
| `01_langchain_integration.ipynb` | First interaction with LLMs via LangChain |
| `02_rag_pipeline.ipynb` | Complete RAG: load docs, chunk, embed, store, query with context |
| `03_security_guardrails.ipynb` | Metadata-level access control, input/output guardrails, prompt injection defense |
| `04_performance_evaluation.ipynb` | Semantic caching, custom callbacks, Langfuse tracing |

**Supporting files:** sample documents under `docs/dummy-knowledge/` (including Peraturan Perusahaan PT Lore Ipsum), bootcamp curriculum, and sample text files in `data/`.

## Prerequisites

- **Python >= 3.10** (see `.python-version`)
- **Google AI Studio API key** (free) — for Gemini models
- **Langfuse account** (free, optional) — for LLM tracing

## Installation

```bash
# 1. Clone the repo
git clone <repo-url>
cd f5-kuncie-llm

# 2. Create environment (uses uv — fast Python package manager)
uv sync

# 3. Copy environment variables
cp .env.example .env
```

## Getting API Keys

**Google Gemini API** (required):

1. Go to [Google AI Studio](https://aistudio.google.com/) > Get API key
2. Add to `.env`: `GOOGLE_API_KEY=AIzaSy...`

**Langfuse** (optional, for tracing):

1. Sign up at [cloud.langfuse.com](https://cloud.langfuse.com)
2. Settings > API Keys > create new keys
3. Add to `.env`:

```
LANGFUSE_PUBLIC_KEY=pk-lf-...
LANGFUSE_SECRET_KEY=sk-lf-...
```

## Usage

```bash
# Start Jupyter Lab
uv run jupyter lab
```

Open the notebooks in order from `notes/`:

1. **01_langchain_integration.ipynb** — Hello world with Gemini
2. **02_rag_pipeline.ipynb** — Build your RAG pipeline step by step
3. **03_security_guardrails.ipynb** — Add safety layers
4. **04_performance_evaluation.ipynb** — Cache and evaluate

> Notebook 02 uses the free Gemini tier. You may hit rate limits when embedding many chunks — the code includes `time.sleep()` delays to stay within the 100 req/min quota.

## Dependencies

| Package | Purpose |
|---|---|
| `langchain-google-genai` | Gemini LLM + embeddings |
| `langchain-qdrant` / `qdrant-client` | Vector database (in-memory) |
| `langchain-text-splitters` | Document chunking |
| `langfuse` | LLM tracing dashboard |
| `deepeval` | RAG evaluation metrics |
| `jupyterlab` | Notebook environment |
| `python-dotenv` | Environment variable management |

Full list in `pyproject.toml`.

## Project Structure

```
.
├── notes/                          # Jupyter notebooks
│   ├── 01_langchain_integration.ipynb
│   ├── 02_rag_pipeline.ipynb
│   ├── 03_security_guardrails.ipynb
│   └── 04_performance_evaluation.ipynb
├── docs/
│   ├── dummy-knowledge/            # Sample documents for RAG
│   │   ├── Peraturan-Perusahaan-LoreIpsum.txt
├── .env                            # API keys (git-ignored)
├── .env.example                    # Template for .env
├── pyproject.toml                  # Dependencies
├── uv.lock                         # Lockfile for uv
├── AGENTS.md                       # Project instructions for AI coding assistants
└── README.md                       # This file
```

## Notes

- **Not for production use** — this is educational material. Qdrant runs in-memory only.
- The dummy-knowledge documents are fictional, created specifically for this bootcamp.
- Data files and embeddings are kept in `data/` (tracked as needed).
