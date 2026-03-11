# Jupyter Notebook – Beginner's Guide

A quick-reference guide covering everything you need to get productive with Jupyter Notebooks.

---

## Table of Contents

- [Jupyter Notebook – Beginner's Guide](#jupyter-notebook--beginners-guide)
  - [Table of Contents](#table-of-contents)
  - [What is Jupyter?](#what-is-jupyter)
  - [Key Concepts](#key-concepts)
  - [JupyterLab vs Jupyter Notebook vs VS Code](#jupyterlab-vs-jupyter-notebook-vs-vs-code)
  - [Cells](#cells)
    - [Code Cells](#code-cells)
    - [Markdown Cells](#markdown-cells)
  - [Essential Keyboard Shortcuts](#essential-keyboard-shortcuts)
    - [Command Mode](#command-mode)
    - [Edit Mode](#edit-mode)
  - [Running Code](#running-code)
    - [Execution Order Matters](#execution-order-matters)
    - [Restarting the Kernel](#restarting-the-kernel)
    - [Run All Cells](#run-all-cells)
  - [Markdown in Notebooks](#markdown-in-notebooks)
    - [Basic Formatting](#basic-formatting)
    - [Code Blocks](#code-blocks)
    - [Tables](#tables)
    - [Math (LaTeX)](#math-latex)
  - [Working with Output](#working-with-output)
    - [Display Types](#display-types)
    - [Suppressing Output](#suppressing-output)
    - [Clearing Output](#clearing-output)
  - [Magic Commands](#magic-commands)
  - [Shell Commands](#shell-commands)
  - [Common Pitfalls](#common-pitfalls)
    - [1. Out-of-order execution](#1-out-of-order-execution)
    - [2. Hidden state](#2-hidden-state)
    - [3. Large outputs](#3-large-outputs)
    - [4. Not saving](#4-not-saving)
    - [5. Kernel dies](#5-kernel-dies)
  - [Tips \& Best Practices](#tips--best-practices)

---

## What is Jupyter?

Jupyter Notebook is an interactive computing environment that lets you combine **live code**, **rich text** (Markdown), **equations** (LaTeX), **visualizations**, and **narrative** in a single document (`.ipynb` files).

The name "Jupyter" comes from **Ju**lia + **Py**thon + **R** — the three original languages it supported. Today it supports many more via _kernels_.

---

## Key Concepts

| Term                | Meaning                                                                          |
| ------------------- | -------------------------------------------------------------------------------- |
| **Notebook**        | A `.ipynb` file containing an ordered list of cells                              |
| **Cell**            | A single block of code or text — the basic unit of a notebook                    |
| **Kernel**          | The process that runs your code (e.g., a Python interpreter)                     |
| **Output**          | The result displayed below a code cell after execution                           |
| **Execution order** | Cells can be run in any order; the number next to `In [n]` shows when it was run |

---

## JupyterLab vs Jupyter Notebook vs VS Code

| Feature        | JupyterLab            | Jupyter Notebook (Classic) | VS Code            |
| -------------- | --------------------- | -------------------------- | ------------------ |
| Interface      | Full IDE-like         | Single notebook            | Full IDE           |
| File browser   | Yes                   | Limited                    | Yes                |
| Terminal       | Built-in              | No                         | Built-in           |
| Extensions     | JupyterLab extensions | Limited                    | VS Code extensions |
| Launch command | `jupyter lab`         | `jupyter notebook`         | Open `.ipynb` file |

All three work with the same `.ipynb` file format. Use whichever you prefer.

---

## Cells

Notebooks have two main cell types:

### Code Cells

- Contain executable code (Python, by default).
- Run a cell to see its output displayed directly below.
- The last expression in a cell is automatically displayed (no `print()` needed).

```python
# This will display 42 below the cell
40 + 2
```

### Markdown Cells

- Contain formatted text using Markdown syntax.
- Support **bold**, _italic_, `code`, lists, tables, images, links, and LaTeX math.
- "Run" a Markdown cell to render it.

---

## Essential Keyboard Shortcuts

Jupyter has two modes:

- **Command mode** (blue border) — press `Esc` to enter. Navigates between cells.
- **Edit mode** (green border) — press `Enter` to enter. Edits cell content.

### Command Mode

| Shortcut      | Action                      |
| ------------- | --------------------------- |
| `Enter`       | Switch to edit mode         |
| `A`           | Insert cell **above**       |
| `B`           | Insert cell **below**       |
| `DD`          | **Delete** current cell     |
| `M`           | Change cell to **Markdown** |
| `Y`           | Change cell to **Code**     |
| `↑` / `↓`     | Move between cells          |
| `Shift+Enter` | Run cell & move to next     |
| `Z`           | Undo cell deletion          |
| `Shift+M`     | Merge selected cells        |

### Edit Mode

| Shortcut      | Action                  |
| ------------- | ----------------------- |
| `Esc`         | Switch to command mode  |
| `Shift+Enter` | Run cell & move to next |
| `Ctrl+Enter`  | Run cell (stay in cell) |
| `Alt+Enter`   | Run cell & insert below |
| `Tab`         | Code completion         |
| `Shift+Tab`   | Show tooltip/docstring  |

> **VS Code note:** Shortcuts differ slightly in VS Code. `Ctrl+Enter` runs the current cell, `Shift+Enter` runs and advances. Use the Command Palette (`Cmd+Shift+P`) and search "Notebook" to see all commands.

---

## Running Code

### Execution Order Matters

Cells can be run in any order. The kernel maintains a single global state, so:

```python
# Cell 1
x = 10

# Cell 2
x = 20

# Cell 3
print(x)  # Output depends on which of Cell 1 or 2 was run LAST
```

### Restarting the Kernel

If things get confusing, restart the kernel to clear all variables:

- **JupyterLab:** Kernel → Restart Kernel
- **VS Code:** Click the restart button (↻) in the notebook toolbar

### Run All Cells

To run the entire notebook top-to-bottom:

- **JupyterLab:** Run → Run All Cells
- **VS Code:** "Run All" button in the toolbar

---

## Markdown in Notebooks

### Basic Formatting

```markdown
# Heading 1

## Heading 2

### Heading 3

**bold text**
_italic text_
`inline code`

- bullet list
- another item

1. numbered list
2. second item

[Link text](https://example.com)

![Image alt text](image_url)
```

### Code Blocks

````markdown
```python
def hello():
    print("Hello!")
```
````

### Tables

```markdown
| Column A | Column B |
| -------- | -------- |
| value 1  | value 2  |
```

### Math (LaTeX)

```markdown
Inline: $E = mc^2$

Block:

$$
\sum_{i=1}^{n} x_i = x_1 + x_2 + \ldots + x_n
$$
```

---

## Working with Output

### Display Types

Jupyter can render many output types:

| Type       | How                                                             |
| ---------- | --------------------------------------------------------------- |
| Text       | `print()` or last expression                                    |
| HTML       | `from IPython.display import HTML`                              |
| Images     | `from IPython.display import Image`                             |
| DataFrames | Just type the variable name (pandas auto-renders as HTML table) |
| Plots      | matplotlib / plotly / seaborn render inline                     |

### Suppressing Output

End a line with a semicolon to suppress the automatic display:

```python
x = 42;  # Nothing displayed
```

### Clearing Output

- **JupyterLab:** Edit → Clear All Outputs
- **VS Code:** Right-click → Clear Cell Outputs

---

## Magic Commands

Magic commands are special Jupyter commands prefixed with `%` (line) or `%%` (cell).

| Command               | Description                               |
| --------------------- | ----------------------------------------- |
| `%timeit x = 1+1`     | Time a single statement (runs many times) |
| `%%timeit`            | Time an entire cell                       |
| `%time`               | Time a single run                         |
| `%who`                | List all variables                        |
| `%whos`               | List variables with details               |
| `%reset`              | Clear all variables                       |
| `%matplotlib inline`  | Show matplotlib plots inline              |
| `%load_ext`           | Load a Jupyter extension                  |
| `%%writefile file.py` | Write cell contents to a file             |
| `%run script.py`      | Run an external Python script             |
| `%history`            | Show command history                      |

---

## Shell Commands

Prefix a line with `!` to run shell commands:

```python
!pip install pandas
!ls -la
!echo "Hello from the shell"
```

You can capture output into a Python variable:

```python
files = !ls
print(files)
```

---

## Common Pitfalls

### 1. Out-of-order execution

Running cells in a non-linear order leads to confusing state. If something feels wrong, **Restart & Run All**.

### 2. Hidden state

Variables persist even after you delete the cell that created them. Restart the kernel if you deleted important cells.

### 3. Large outputs

Printing huge lists or DataFrames can freeze the browser. Use `.head()` for DataFrames and slice large collections.

### 4. Not saving

Notebooks auto-save, but it's good practice to save manually (`Cmd+S` / `Ctrl+S`) before closing.

### 5. Kernel dies

If the kernel crashes (often from memory issues), restart it. Reduce data size or free memory if it keeps happening.

---

## Tips & Best Practices

1. **Run All before sharing** — Make sure the notebook runs top-to-bottom without errors.
2. **Keep cells small** — Each cell should do one logical thing.
3. **Use Markdown freely** — Explain your thought process between code cells.
4. **Name your notebooks descriptively** — `data_analysis_q1_2026.ipynb` > `Untitled.ipynb`.
5. **Restart & Run All regularly** — Catches hidden-state bugs early.
6. **Put imports at the top** — First cell should have all `import` statements.
7. **Use version control** — `.ipynb` files are JSON and work with Git (though diffs can be noisy).
8. **Clear outputs before committing** — Keeps file sizes small and diffs clean.
