
# ADMET Prediction under Scaffold Split with an Agentic Candidate Filter

## Current Progress

### Phase 1: Environment & Infrastructure — COMPLETE
- Google Colab environment configured
- Google Drive project storage configured
- GitHub repository configured
- Project directory structure created
- Dependencies installed and verified

### Phase 2: Dataset Acquisition & Cleaning — COMPLETE

Datasets:
- Solubility (AqSolDB): 9980 molecules
- Lipophilicity: 4200 molecules
- AMES: 7255 molecules
- BBB: 1965 molecules

Total cleaned molecules: 23400

Cleaning:
- Invalid SMILES removed
- Canonical SMILES generated
- Duplicate molecules handled
- Conflicting BBB labels removed
- Raw datasets preserved

### Phase 3: Data Splitting & Leakage Audit — COMPLETE

Split strategies:
- Random split: 80/10/10
- Bemis-Murcko scaffold split: 80/10/10

Seeds:
- 42
- 123
- 2026

Total configurations: 24

Audit results:
- 24/24 configurations passed
- No molecular overlap between train, validation, and test
- No scaffold overlap in scaffold splits

Audit report:
results/experiments/split_audit_all_24_configurations.csv

### Phase 4: Feature Engineering — COMPLETE

Method:
- RDKit 2D molecular descriptors
- Initial descriptors: 217

Constant feature removal:

| Dataset | Initial Features | Removed | Remaining |
|---------|-----------------|---------|-----------|
| Solubility | 217 | 2 | 215 |
| Lipophilicity | 217 | 9 | 208 |
| AMES | 217 | 2 | 215 |
| BBB | 217 | 6 | 211 |

Missing descriptor values identified and preserved for handling
during model training using train-only imputation.

Processed feature matrices saved:

data/processed/descriptors/
- solubility_descriptors.csv
- lipophilicity_descriptors.csv
- ames_descriptors.csv
- bbb_descriptors.csv

### Current Phase: XGBoost Baseline Modelling

Next task:
- Start with Solubility
- Random split
- Seed 42
- XGBoost regression

Pipeline:
1. Load saved descriptor matrix
2. Load corresponding train/validation/test split
3. Separate features, target, and SMILES
4. Median imputation fitted only on training data
5. Train XGBoost
6. Model selection using validation set
7. Evaluate once on test set
8. Calculate MAE, RMSE, and R2
9. Save model and results

After pipeline verification:
- Reuse pipeline for remaining datasets
- Random and scaffold splits
- All three seeds

### Future Phases

1. XGBoost baseline experiments
2. SMILES LSTM
3. Compact GCN
4. Random vs scaffold performance comparison
5. Model comparison
6. Candidate pool preparation
7. Candidate overlap audit
8. Agentic screening system
9. Screening budget experiments
10. Streamlit dashboard
11. Final analysis and report

## Research Scope

- Four ADMET endpoints
- Two deep learning models: SMILES LSTM and compact GCN
- XGBoost descriptor baseline
- Random and scaffold splits
- Three seeds
- Agentic candidate filtering and budget evaluation

No transformers, molecular generators, or reinforcement learning planned.
