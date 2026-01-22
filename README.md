# Credit Risk ML Project

This repository contains a **single, end-to-end Jupyter notebook** implementing a supervised credit-risk (probability of default) modeling pipeline.

The project is designed for **academic review and grading**:
- fully reproducible,
- deterministic outputs,
- beginner-friendly explanations,
- and a single, verifiable execution path.

All modeling logic, explanations, and decisions live in **one notebook**:
`notebooks/credit_risk_project.ipynb`.

---

## Project Structure

```yaml
credit-risk-ml-mif/
│
├── notebooks/
│ └── credit_risk_project.ipynb ← all code + explanations
│
├── data/
│ ├── lending_club_train.csv ← REQUIRED (uploaded by reviewer)
│ └── lending_club_test.csv ← REQUIRED (uploaded by reviewer)
│
├── outputs/
│ ├── final_report.md
│ ├── model_card.md
│ ├── outputs_manifest.txt
│ ├── *.csv, *.png ← generated artifacts
│
├── requirements.txt
└── README.md
```

---

## Inputs and Outputs Policy

### Inputs
The notebook **reads exactly two input files**:
- `data/lending_club_train.csv`
- `data/lending_club_test.csv`

These files are **not included** in the repository and must be uploaded manually in Google Colab.

No other data files are used.

---

### Outputs
- All results are written to the `outputs/` folder
- Outputs are **regenerated on every full run**
- Existing outputs are **overwritten**
- Outputs are **derived artifacts only** (no raw data)

A deterministic manifest is generated at:
`outputs/outputs_manifest.txt`

```yaml
The manifest records:
- git commit hash
- file names
- file sizes
- SHA256 hashes
- short purpose descriptions
```

**The manifest is the single source of truth** for what was generated in a given run.

---

## How to Run the Project (Google Colab — Single Supported Method)

This project is intended to be reviewed and executed **only in Google Colab**.

Follow the steps below **exactly in order**.

---

### Step 1 — Open Google Colab

Go to:
https://colab.research.google.com

---

### Step 2 — Clone the repository (submission snapshot)

In a **new Colab notebook**, run this cell:

```bash
!git clone https://github.com/Jannikwendt/credit-risk-ml-mif.git
%cd credit-risk-ml-mif
!git fetch --all --tags
!git checkout submission-v1
```

**Why this matters:**
`submission-v1` is a frozen snapshot of the submitted project.
Using it guarantees identical logic, explanations, and outputs.

---

### Step 3 — Upload the required data files
The notebook will not run without data.

You must upload:
- `lending_club_train.csv`
- `lending_club_test.csv`

Run this cell:

```python
from google.colab import files
files.upload()
```

After uploading, move the files into the correct folder:

```bash
!mkdir -p data
!mv lending_club_train.csv data/
!mv lending_club_test.csv data/
```

Verify the files are in the correct location:

```bash
!ls data
```

You should see:
```
lending_club_train.csv
lending_club_test.csv
```

---

### Step 4 — Install dependencies
Install the required Python packages:

```bash
!pip install -r requirements.txt
```

---

### Step 5 — Open the notebook (view code + explanations)
In the Colab file browser (left sidebar):
1. Open `notebooks/credit_risk_project.ipynb`

To ensure all code cells are visible:
- Click **View** → **Expand sections**

The notebook contains:
- plain-English explanations,
- glossary definitions,
- step-by-step modeling logic,
- and extensive comments for non-coders.

---

### Step 6 — Run the notebook end-to-end
In the opened notebook:
1. Click **Runtime** → **Restart runtime**
2. Click **Runtime** → **Run all**

This executes the full pipeline from raw data to final outputs.

---

### Step 7 — Verify successful execution
After the notebook finishes, run:

```bash
!ls outputs
!cat outputs/outputs_manifest.txt
```

A successful run means:
- no execution errors
- `outputs/` contains CSV, PNG, and Markdown files
- `final_report.md` exists and summarizes results in plain English
- `outputs_manifest.txt` lists all generated artifacts with SHA256 hashes

---

## How to Review Results (No Coding Required)
If you only want to review results:
- Open `outputs/final_report.md` for a human-readable summary
- Open `outputs/model_card.md` for modeling assumptions and limitations
- Use `outputs/outputs_manifest.txt` to verify reproducibility

---

## Important Notes
- **Fresh generation**: Outputs are overwritten on every run
- **Input isolation**: Only the two CSV files in `data/` are used
- **No data leakage**: `lending_club_test.csv` is an unlabeled hold-out set and is never used for training or tuning
- **Reproducibility**: SHA256 hashes act as digital fingerprints for all exported artifacts

---

## Summary
If you:
1. clone the repo,
2. upload the two CSV files,
3. run the notebook,

you will reproduce exactly the same results as the submitted project.
