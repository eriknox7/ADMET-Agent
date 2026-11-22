# ADMET-Agent

## Project

ADMET Prediction under Scaffold Split with an Agentic Candidate Filter.

## Research Objective

Compare:

- Graph Convolutional Network (GCN)
- SMILES-based LSTM
- Molecular-descriptor XGBoost

Across four ADMET endpoints:

- Solubility — Regression
- Lipophilicity — Regression
- AMES Mutagenicity — Classification
- Blood-Brain Barrier Penetration — Classification

Evaluate Random and Bemis-Murcko Scaffold splits and investigate
whether an agentic candidate filter can reduce predictor calls
while preserving shortlist quality.

## Project Structure

- `src/` — Modular source code
- `notebooks/` — Development notebooks
- `app/` — Streamlit application
- `config/` — Experiment configuration
- `reports/` — Documentation and reports

Large datasets, model checkpoints, results and logs are stored
persistently in Google Drive and excluded from Git.

## Environment

Development and experiments are performed using Google Colab.
GPU acceleration is used whenever available.

## Reproducibility

Experiments will record:

- Dataset identifiers
- Split strategy
- Random seed
- Model configuration
- Evaluation metrics
- Runtime
- Experiment notes

See `PROJECT_STATUS.md` for the current progress.