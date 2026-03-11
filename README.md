# Jupyter Learning Project

A beginner-friendly project for learning Jupyter Notebooks with Python.

## Project Structure

```
├── main.py                  # Simple Python entry point
├── pyproject.toml           # Project configuration & dependencies
├── notebooks/
│   ├── test_notebook.ipynb  # Quick smoke-test notebook
│   └── jupyter_tutorial.ipynb  # Interactive Jupyter tutorial (start here!)
├── JUPYTER_GUIDE.md         # Jupyter cheat-sheet & reference
└── README.md
```

## Prerequisites

- Python 3.14+
- [uv](https://docs.astral.sh/uv/) (recommended) or pip

## Getting Started

### 1. Install dependencies

```bash
uv sync
```

Or with pip:

```bash
pip install -e .
```

### 2. Launch JupyterLab

```bash
uv run jupyter lab
```

This opens JupyterLab in your browser. Navigate to `notebooks/jupyter_tutorial.ipynb` to start the interactive tutorial.

### 3. Run in VS Code (alternative)

1. Open the project folder in VS Code.
2. Install the **Jupyter** extension (if not already installed).
3. Open any `.ipynb` file and run cells directly in the editor.

## Resources

| Resource                                                             | Description                                   |
| -------------------------------------------------------------------- | --------------------------------------------- |
| [JUPYTER_GUIDE.md](JUPYTER_GUIDE.md)                                 | Quick-reference guide covering Jupyter basics |
| [notebooks/jupyter_tutorial.ipynb](notebooks/jupyter_tutorial.ipynb) | Hands-on interactive tutorial notebook        |
| [Jupyter Documentation](https://jupyter.org/documentation)           | Official Jupyter docs                         |
| [Python Tutorial](https://docs.python.org/3/tutorial/)               | Official Python tutorial                      |
