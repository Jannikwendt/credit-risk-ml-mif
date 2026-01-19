# Model Card

## Executive Summary
- Predicts probability of default to support lending decisions.
- Final model selected by highest validation AUC for generalization.
- Threshold policy balances approval volume and default risk.
- Decisioning is grounded in transparent payoff assumptions.

## Data & Split
- Train rows: 7596
- Validation rows: 2533
- Test rows: 2533
- Target prevalence (train): 0.1929
- Target prevalence (validation): 0.1927
- Random state: 42

## Feature Engineering
- Affordability: installment_to_income, loan_to_income
- Leverage: revol_balance_util, revol_balance_to_income
- Stability/experience: open_to_total_acc, recent_inquiry_flag
- Nonlinear: log_annual_inc, sqrt_dti

## Models Compared
Model performance is summarized in `model_comparison_validation.csv`. The final model is selected based on validation AUC, with AUC gap used to monitor overfitting risk.

## Final Policy (Validation)
- Final model: Random Forest
- Validation AUC: 0.6939
- Validation RMSE: 0.3793
- Optimal threshold: 0.29
- Approval rate: 0.820
- Expected value: -14

## Confusion Matrices (Validation)
- Threshold 0.50: approvals=2529, defaults among approved=486, approval_rate=0.998
- Optimal threshold: approvals=2076, defaults among approved=303, approval_rate=0.820
- Full tables are saved in `confusion_matrix_validation_050.csv` and `confusion_matrix_validation_optimal.csv`.

## Limitations & Next Steps
- Payoff assumptions are stylized; calibrate to bank economics.
- Threshold chosen on validation; test remains untouched for final audit.
- Monitor drift and recalibrate thresholds as conditions change.
- Consider calibration and fairness analyses as follow-on work.

## Reproducibility
- Run `notebooks/credit_risk_project.ipynb` → Restart Kernel & Run All.
