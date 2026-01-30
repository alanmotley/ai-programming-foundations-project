# AI Programming Foundations Project: Reproducible Data Workflow

**Author:** Frank Allen Motley  
**Dataset:** Titanic (Seaborn example dataset) — https://raw.githubusercontent.com/mwaskom/seaborn-data/master/titanic.csv  

This project demonstrates a complete, reproducible data workflow using Python, NumPy, Pandas, and Matplotlib/Seaborn. It loads a real dataset, cleans and transforms it with reusable functions, performs exploratory analysis, creates labeled visualizations, and summarizes insights with notes on limitations and responsible data handling.

## What I built
- `data_workflow.ipynb` — end-to-end workflow (ingestion → cleaning → EDA → visualizations → interpretation)
- `module_summary.pdf` — written report with academic citations and references
- `requirements.txt` — reproducible dependency list for running the notebook

## How to run
### Option A: Conda (recommended for clean reproducibility)
```bash
conda create -n aiwf python=3.11 -y
conda activate aiwf
pip install -r requirements.txt
python -m ipykernel install --user --name aiwf --display-name "Python (aiwf)"
jupyter notebook
```

In Jupyter: **Kernel → Change Kernel → Python (aiwf)**, then **Restart & Run All**.

### Option B: Pip (existing environment)
```bash
pip install -r requirements.txt
jupyter notebook
```

## Outputs
- Figures are saved to `./figures/`:
  - `figure1_survival_by_sex.png`
  - `figure2_survival_by_class.png`
  - `figure3_age_by_survival.png`

## Reproducibility notes
- This project is tested with **NumPy 1.x** (specifically `numpy==1.26.4`).
- If you see an error like: *“a module compiled using NumPy 1.x cannot be run in NumPy 2.x”*, create a clean environment and install from `requirements.txt` (NumPy is pinned to 1.x to avoid binary compatibility issues).

To regenerate dependencies from your environment:
```bash
pip freeze > requirements.txt
```

## Responsible practice (bias and data quality)
- **Imputation risk:** Filling missing ages with the median and missing categorical values with the mode can reduce variance and may shift group comparisons.
- **Historical/selection bias:** The Titanic passenger list is not representative of broader populations; outcomes reflect a specific historical and social context.
- **Next steps to reduce risk:** Try sensitivity checks (e.g., compare results with/without imputation), stratified analysis, and clearer documentation of missingness patterns.

## Git / GitHub workflow
This repository includes multiple commits and at least one additional branch (`dev`) to demonstrate professional version control.

## Future integration reflections
- **How ML workflow changes:** Add train/validation/test splits, prevent leakage (fit preprocessing on train only), and evaluate models with appropriate metrics.
- **Neural network preparation:** Normalize/scale numeric features, encode categoricals consistently, and define a stable feature schema; handle missingness with a pipeline.
- **Agentic automation potential:** An agent could automate data profiling, generate EDA summaries/plots, run reproducibility checks, and draft a report while logging decisions for review.
