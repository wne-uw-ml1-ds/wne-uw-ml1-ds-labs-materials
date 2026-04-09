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

**Install dependencies and launch JupyterLab:**

```bash
uv sync
uv run jupyter lab
```

## Dependencies

- `numpy`, `pandas` – data manipulation
- `matplotlib`, `seaborn` – visualization
- `scikit-learn` – machine learning models and utilities
- `scipy` – scientific computing
- `imbalanced-learn` – handling imbalanced datasets
- `jupyter`, `ipykernel` – notebook environment
