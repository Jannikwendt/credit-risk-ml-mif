# Model Card

**Project:** Credit Risk PD Model (Lending Club)

## Data
- Training set: 10129 rows
- Test set: 2533 rows
- Target prevalence (train): 0.1928

## Final model
- Model: Random Forest
- Validation AUC: 0.6939
- Validation RMSE: 0.3793

## Threshold policy (validation)
- Optimal threshold: 0.29
- Approval rate: 0.820
- Expected value: -14

## Business interpretation
- Defaults carry materially higher cost than missed good loans.
- Threshold policy prioritizes avoiding high-risk approvals.
- Approval rate reflects operational capacity under chosen costs.
- AUC gap provides a check on overfitting risk.
- Threshold sensitivity indicates policy stability.

## Limitations
- Payoff assumptions are stylized and not bank-calibrated.
- Threshold chosen on validation; test set remains untouched.
- Historical data may not reflect future macro conditions.
- Model performance depends on feature availability and quality.

## Reproducibility
- Run `notebooks/credit_risk_project.ipynb` → Restart Kernel & Run All.
