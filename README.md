# WNE UW ML1 – Data Science Labs Materials

Lab notebooks for the Machine Learning 1 course at WNE UW.

## Lecture Materials

Slides and lecture notes are available here:
[Lecture Materials (Google Slides)](https://docs.google.com/presentation/d/1jtaqGdD8j_poQTZuZAgxJ1Qwl9Up7FS_KchoY3cT_jY/edit?usp=sharing)

## Notebooks

| Notebook | Topics |
|---|---|
| `notebooks/knn.ipynb` | K-Nearest Neighbors |
| `notebooks/svm.ipynb` | Support Vector Machines |
| `notebooks/core_ml_techniques.ipynb` | Core ML techniques: preprocessing, feature selection, ensembles, model evaluation |

## Setup

This project uses [uv](https://docs.astral.sh/uv/) for dependency management.

### Installing uv

**macOS / Linux:**

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**Windows (PowerShell):**

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

After installation, restart your terminal.

### Install dependencies and launch JupyterLab

```bash
uv sync
uv run jupyter lab
```

> **Recommendation:** While JupyterLab/Notebook works fine, we recommend running notebooks inside a full IDE such as [VS Code](https://code.visualstudio.com/), [PyCharm](https://www.jetbrains.com/pycharm/), or [Cursor](https://www.cursor.com/). IDEs provide better code completion, debugging, and Git integration. After running `uv sync`, select the `.venv` environment as your Python interpreter in the IDE.

## Contributing / Development

### Pre-commit hooks

This project uses [pre-commit](https://pre-commit.com/) to enforce code quality on every commit. Install the hooks after syncing dependencies:

```bash
uv sync --dev
uv run pre-commit install
```

The following hooks run automatically on `git commit`:

| Hook | What it does |
|---|---|
| `trailing-whitespace` | Strips trailing whitespace from all files |
| `end-of-file-fixer` | Ensures files end with a single newline |
| `check-yaml` / `check-toml` | Validates YAML and TOML syntax |
| `check-merge-conflict` | Catches leftover merge conflict markers |
| `ruff` | Lints and auto-fixes Python files (E, F, W, I rules) |
| `ruff-format` | Formats Python files (Black-compatible) |
| `nbqa-ruff` | Runs ruff linting on notebook cells |
| `nbqa-ruff-format` | Runs ruff formatter on notebook cells |
| `nbstripout` | Strips notebook outputs before committing (keeps output counts) |

To run all hooks manually against all files:

```bash
uv run pre-commit run --all-files
```

### Linting rules

Ruff is configured in `pyproject.toml` with:
- **Line length:** 120 characters
- **Rules:** `E` (pycodestyle errors), `F` (pyflakes), `W` (pycodestyle warnings), `I` (isort)
- **Notebook-specific ignores:** `E402` (import-not-at-top, expected in cells), `E501` (line-too-long, alignment-heavy print statements)

## Dependencies

- `numpy`, `pandas` – data manipulation
- `matplotlib`, `seaborn` – visualization
- `scikit-learn` – machine learning models and utilities
- `scipy` – scientific computing
- `imbalanced-learn` – handling imbalanced datasets
- `jupyter`, `ipykernel` – notebook environment

### Dev dependencies

- `ruff` – linter and formatter
- `pre-commit` – git hook manager
- `nbqa` – run linters on Jupyter notebooks
- `nbstripout` – strip notebook outputs before committing
