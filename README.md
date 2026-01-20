## Credit Risk ML Project

This repository contains a single, end-to-end notebook for a supervised credit risk (PD) modeling workflow. The notebook is fully reproducible and produces a deterministic set of outputs for grading and review.

### How to Run
- Open `notebooks/credit_risk_project.ipynb`.
- Restart Kernel & Run All.
- The notebook reads only:
  - `data/lending_club_train.csv`
  - `data/lending_club_test.csv`

### Outputs Policy
Outputs are regenerated on Run All and overwrite existing artifacts; commit outputs only for the final snapshot; manifest is deterministic.

All outputs are generated deterministically by the notebook and written to `outputs/`.
The export step produces a manifest (`outputs/outputs_manifest.txt`) that records:
- git commit hash
- file list, sizes, SHA256 hashes, and brief purpose

Expected artifacts include model comparison tables, tuning tables, threshold sweep outputs, decisioning curves, and a model card. The outputs are derived artifacts only (no raw data), and the manifest is the single source of truth for what was exported in a given run.
