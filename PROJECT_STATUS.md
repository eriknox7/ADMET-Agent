# ADMET Prediction under Scaffold Split with an Agentic Candidate Filter

## Project Status

### Completed

- [x] Google Drive and GitHub project setup
- [x] Environment setup and dependency verification
- [x] Dataset acquisition
- [x] Raw datasets preserved
- [x] Initial data audit
- [x] Canonical SMILES processing
- [x] Duplicate molecule analysis
- [x] Conflicting-label analysis
- [x] Data cleaning
- [x] Cleaned datasets saved
- [x] Bemis-Murcko scaffold extraction implemented
- [x] Acyclic molecule grouping handled
- [x] Scaffold splitting implemented
- [x] Solubility scaffold split generated (Seed 42)
- [x] Split sizes verified
- [x] Scaffold leakage audit passed

### Dataset Summary

| Dataset | Samples | Task |
|---|---:|---|
| Solubility | 9980 | Regression |
| Lipophilicity | 4200 | Regression |
| AMES | 7255 | Classification |
| BBB | 1965 | Classification |
| Total | 23400 | |

### Current Experimental Split

Dataset: Solubility

Split strategy: Bemis-Murcko Scaffold Split

Seed: 42

| Split | Samples | Percentage |
|---|---:|---:|
| Train | 7984 | 80.00% |
| Validation | 998 | 10.00% |
| Test | 998 | 10.00% |

### Leakage Audit

| Comparison | Scaffold Overlap | Result |
|---|---:|---|
| Train vs Validation | 0 | PASS |
| Train vs Test | 0 | PASS |
| Validation vs Test | 0 | PASS |

### Current Stage

Data preprocessing and experimental split preparation.

### Next Steps

- [ ] Implement random splitting
- [ ] Validate random split implementation
- [ ] Generate random and scaffold splits for all four datasets
- [ ] Use three random seeds: 42, 123, 2026
- [ ] Perform molecule and scaffold leakage audits
- [ ] Save split files and metadata
- [ ] Begin baseline model experiments

## Storage

Raw data, cleaned data, experimental splits, artifacts, and results are stored in Google Drive.

Code, notebooks, and documentation are version-controlled using GitHub.
