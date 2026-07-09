# F5 - Kuncie LLM

## Environment
- Use `uv` for everything — never `pip` directly.
- `uv run python` for scripts, `uv run jupyter lab` for notebooks.
- Python 3.14 (see `.python-version`), requires `>=3.10`.
- Virtual env at `.venv/` — managed by uv, do not touch directly.

## Commands
| Action | Command |
|---|---|
| Add dependency | `uv add <package>` |
| Sync environment | `uv sync` |
| Run Python script | `uv run python <file>` |
| Run Jupyter Lab | `uv run jupyter lab` |

## Project Layout
- `main.py` — placeholder entrypoint, run via `uv run python main.py`.
- `docs/` — bootcamp curriculum (JSON source of truth + XLSX/PDF derivatives).
- `notes/` — empty, for participant work.
- No tests, no CI, no linting configured.

## Dependencies
LangChain (google-genai, azure-ai, qdrant, openai), JupyterLab, Qdrant, python-dotenv.
