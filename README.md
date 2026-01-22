## Credit Risk ML Project

This repository contains a single, end-to-end notebook for a supervised credit risk (PD) modeling workflow. The notebook is fully reproducible and produces a deterministic set of outputs for grading and review.

---

## Run & Reproduce in Google Colab (Foolproof)

This is the only supported Colab workflow. It avoids the common `../data/...` FileNotFoundError by cloning the repo so the folder structure matches the notebook’s paths.

### 1) Open Colab
Go to Google Colab and create a new notebook:
https://colab.research.google.com → New Notebook

### 2) Clone the repository (frozen snapshot)
Run this cell (copy/paste):

```bash
!git clone https://github.com/Jannikwendt/credit-risk-ml-mif.git
%cd credit-risk-ml-mif
!git fetch --all --tags
!git checkout submission-v1
```
