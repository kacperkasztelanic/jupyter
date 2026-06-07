# Repository Guidelines

## Project Structure & Module Organization

This is a small Python learning project centered on Jupyter notebooks.

- `main.py` contains the simple Python entry point.
- `notebooks/` contains runnable tutorial notebooks, including `jupyter_tutorial.ipynb` and `test_notebook.ipynb`.
- `README.md` explains setup and first-run workflow.
- `JUPYTER_GUIDE.md` is the learner-facing Jupyter reference.
- `pyproject.toml` and `uv.lock` define the Python package metadata and locked dependencies.

Keep new notebooks in `notebooks/`. Add longer written guidance as Markdown at the repository root unless it belongs inside a notebook exercise.

## Build, Test, and Development Commands

Python 3.14+ is required by `pyproject.toml`.

- `uv sync` installs the locked dependencies into the local virtual environment.
- `uv run jupyter lab` starts JupyterLab for working through notebooks.
- `uv run python main.py` runs the Python entry point.
- `pip install -e .` is the fallback install path when `uv` is unavailable.

The project currently has no build step beyond dependency installation.

## Coding Style & Naming Conventions

Use idiomatic Python with 4-space indentation and clear, beginner-friendly names. Prefer small functions and direct examples over clever abstractions because this repository is instructional.

Name notebooks with lowercase words separated by underscores, for example `data_types_intro.ipynb`. Keep notebook headings descriptive and order cells so they can be run top to bottom.

No formatter or linter is configured yet. If adding one, document the command here and avoid broad formatting churn unrelated to the change.

## Testing Guidelines

There is no formal test framework configured. For now, validate changes by running:

```bash
uv run python main.py
```

For notebook changes, open JupyterLab with `uv run jupyter lab`, run the edited notebook from a fresh kernel, and confirm all cells execute in order. Use `notebooks/test_notebook.ipynb` for quick smoke checks.

## Commit & Pull Request Guidelines

Existing commits use short, imperative summaries such as `Add test_notebook` and `Update README.md and JUPYTER_GUIDE.md`. Follow that style: keep the subject concise and state the action.

Pull requests should include a brief description, the files or notebooks changed, and the validation performed. For visual notebook updates, include screenshots or note that the notebook was run successfully from a fresh kernel.

## Security & Configuration Tips

Do not commit local virtual environments, generated caches, notebook checkpoints, macOS metadata, or personal Jupyter configuration. Keep `.venv/`, `__pycache__/`, `.ipynb_checkpoints/`, `.DS_Store`, build outputs, and package artifacts out of version control.
