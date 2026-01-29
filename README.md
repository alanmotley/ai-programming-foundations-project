# AI Programming Foundations Project — Reproducible Data Workflow

## Project Description
This project demonstrates a complete, reproducible data workflow using Python, NumPy, Pandas, and Matplotlib/Seaborn. It loads a real dataset, performs cleaning and transformation with reusable functions, runs exploratory analysis, produces labeled visualizations, and summarizes findings.

## What I Built
- `data_workflow.ipynb`: End-to-end workflow (ingestion → cleaning → EDA → visualization → interpretation)
- `module_summary.pdf`: Written report with citations (APA-style sections)
- `requirements.txt`: Environment snapshot for reproducibility
- `figures/`: Saved visualizations (Figure 1–3)

## Dataset
- Titanic dataset (Seaborn example dataset)  
  Source: https://raw.githubusercontent.com/mwaskom/seaborn-data/master/titanic.csv

## How to Run the Project
1. **Clone the repo** and move into the project folder:
   ```bash
   git clone <your-repo-url>
   cd ai-programming-foundations-project
   ```

2. **Create and activate a virtual environment** (recommended), then install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. **Open the notebook**:
   ```bash
   jupyter notebook
   ```
   Then open `data_workflow.ipynb` and run all cells top-to-bottom.

4. **Generate `requirements.txt` in your environment** (required for submission):
   ```bash
   pip freeze > requirements.txt
   ```

## Responsible Practice: Bias & Data Quality (Reflection)
- **Where bias can be introduced:** Missing-data imputation (e.g., filling ages with a median) can reduce variance and may change group differences. Dropping rows with missing values can also disproportionately remove certain groups if missingness is not random.
- **What I did here:** I used simple, transparent imputation rules (median for numeric, mode for categorical) and kept the limitations explicit in the notebook and report.
- **What I would do next:** Compare results across multiple handling strategies (drop vs. impute; group-wise impute), and document dataset context and limitations more formally (datasheet-style documentation).

## Future Integration Reflections (Required)
- **How this changes for an ML workflow:** I would add train/validation/test splits, define a target variable, and avoid leakage by fitting preprocessing steps on training data only (e.g., via pipelines).
- **Neural network preparation:** I would standardize/normalize numeric features, encode categorical variables, and confirm that input shapes and missing-value handling are consistent for batching.
- **Agentic automation potential:** This workflow is a good candidate for automation (e.g., a small agent that validates schema, checks missingness, regenerates EDA summaries, and exports updated figures/reports on each new data drop).
