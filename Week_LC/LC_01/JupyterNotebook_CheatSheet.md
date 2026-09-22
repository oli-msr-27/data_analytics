# Jupyter Notebook Cheat Sheet

## What is a Jupyter notebook?

A `.ipynb` file is a document made of **cells** that you run individually, backed by a
**kernel** — a live Python process holding all variables, imports, and state in memory.

**Key idea:** the kernel's state reflects the order you *ran* cells in, not the order
they appear in the file. Editing/re-running cells out of order can leave you with stale
state that looks fine on screen but won't reproduce for someone else (or a grader)
opening the notebook fresh.

> Always verify a notebook works correctly with
> **Kernel → Restart Kernel and Run All Cells** before submitting — this wipes the
> kernel and re-runs everything strictly top to bottom.

## Cell types

| Type | Purpose |
|---|---|
| Code | Runs Python code |
| Markdown | Formatted text — headings, bullet lists, tables, images, and raw embedded HTML |
| Raw | Content passed through unmodified — not executed or rendered |

## Magic commands

`%` = line magic (applies to one line). `%%` = cell magic (applies to the whole cell,
must be the first line).

| Command | Type | What it does |
|---|---|---|
| `%pwd` | line | Prints the notebook's current working directory |
| `%who` | line | Lists all variables currently defined in the kernel |
| `%time` | line | Times a single line of code (reports CPU + wall time) |
| `%%time` | cell | Times the entire cell |
| `%%writefile <file>` | cell | Writes the rest of the cell's content to a file instead of executing it |
| `!<command>` | shell escape | Runs a shell command, e.g. `!ls` (Mac/Linux), `!dir` (Windows) |
| `<name>?` | help | Opens the docstring/help for a function or object, e.g. `pd.read_csv?` |
| `<name>??` | help | Like `?` but also shows source code, if available |

### CPU time vs. wall time

- **Wall time** — real-world elapsed time, like a stopwatch
- **CPU time** — actual processor time spent (`user` = your code, `sys` = OS calls like
  file I/O)
- Usually close for simple, single-threaded code. Wall time can be *longer* if the
  process was waiting (e.g. disk/network); CPU time can be *longer* if work was spread
  across multiple cores at once.

## Why cell order matters

Two common failure modes:
1. Running `print(x)` before the cell defining `x = 1` → `NameError`, because from the
   kernel's perspective `x` was never created.
2. Editing a variable in a later cell, then not re-running an earlier cell that depends
   on the old value → silently stale/wrong results.

**Restart Kernel and Run All Cells** is the real correctness check — it's how a grader
or teammate will experience your notebook, since they won't know or replicate whatever
ad-hoc order you happened to run cells in while writing it.
