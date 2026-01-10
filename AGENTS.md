# Repository Guidelines

## Project Structure & Module Organization
- `python/` is the working directory for the course materials. It contains Jupyter notebooks (`L1_nodes.ipynb`, `L2_edges.ipynb`, `L3-L4_cedges_memory.ipynb`, `L5_interrupt.ipynb`, `L6_EmailAgent.ipynb`), helper code like `env_utils.py`, and a local `assets/` folder used by the notebooks.
- `assets/` at the repo root contains shared images and diagrams referenced by documentation.
- `.devcontainer/` provides a preconfigured environment for running the notebooks in a containerized setup.

## Build, Test, and Development Commands
Run these from `python/` unless noted:
- `uv sync` installs dependencies and creates the virtual environment defined by `pyproject.toml`/`uv.lock`.
- `uv run jupyter lab` launches Jupyter Lab without manually activating the venv.
- `pip install -r requirements.txt` is the pip alternative to install runtime dependencies.
- `langgraph dev` starts LangGraph Studio (expects a `.env` with API keys).
- `uv sync --extra dev` installs development tools like `ruff` and `mypy`.

## Coding Style & Naming Conventions
- Python version target is 3.11–3.13.
- Linting configuration lives in `python/pyproject.toml` under `tool.ruff`.
- Prefer snake_case for Python utilities (see `env_utils.py`) and keep notebook names consistent with the lesson numbering pattern (`L1_`, `L2_`, etc.).

## Testing Guidelines
- There is no dedicated test suite in the repository today.
- If you add tests, place them under `python/tests/` and name files `test_*.py`; the Ruff config already treats `tests/*` with relaxed docstring rules.

## Commit & Pull Request Guidelines
- Recent commits use short, lowercase, imperative-style messages (e.g., "include codex in Dockerfile"). Keep messages concise without prefixes unless a change warrants it.
- PRs should describe the learning impact, link related issues (if any), and include screenshots for notebook/asset changes.

## Security & Configuration Tips
- Store API keys in `python/.env` (e.g., `OPENAI_API_KEY`, optional `LANGSMITH_API_KEY`). Do not commit secrets or generated artifacts.
