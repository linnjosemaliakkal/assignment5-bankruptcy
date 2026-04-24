# Assignment 5 – Results Summary  
**Name:** Linn Jose  
**Student ID:** 100998224  

---

## Problem Statement
- Objective: Predict whether a company will go bankrupt using financial indicators.
- Type: Binary classification problem (0 = No, 1 = Yes).

---

## Dataset Summary
- Dataset contains financial ratios of companies.
- Total observations: ~6800+
- Number of features: Multiple financial indicators.
- Target variable: Bankruptcy? (0 or 1)

---

## Class Imbalance
- Highly imbalanced dataset.
- Majority class: Non-bankrupt (~96%)
- Minority class: Bankrupt (~4%)
- Imbalance requires special handling.

---

## Discrimination Metric
- Metric used: **PR-AUC (Precision-Recall AUC)**
- Reason:
  - Better for imbalanced datasets.
  - Focuses on detecting minority class.
- ROC-AUC also reported for comparison.

---

## Calibration Metric
- Metric used: **Brier Score**
- Measures probability accuracy.
- Lower Brier score = better calibrated model.

---

## Feature Selection
- Two feature sets tested:
  - Full feature set (A)
  - Reduced feature set (B)
- Reduced set simplified model but slightly decreased performance.

---

## Experiment Results

| Experiment | Model              | Feature Set | Val PR-AUC | Overfit Gap |
|------------|------------------|-------------|------------|-------------|
| 1          | Logistic         | A           | Low        | Low         |
| 2          | XGB Base         | A           | ~0.49      | High        |
| 3          | XGB Imbalance    | A           | ~0.49      | High        |
| 4          | XGB Tuned        | A           | ~0.52      | Medium      |
| 5          | XGB Reduced      | B           | ~0.38      | High        |

---

## Winning Model
- Selected model: **XGBoost Tuned**
- Reason:
  - Highest validation PR-AUC (~0.52)
  - Better balance between bias and variance
  - Improved generalization

---

## Final Test Results
- Test PR-AUC: ~0.52
- Test ROC-AUC: ~0.95
- Test Brier Score: ~0.02

---

## Confusion Matrix
- True Negatives (TN): 987  
- False Positives (FP): 3  
- False Negatives (FN): 24  
- True Positives (TP): 9  

---

## Calibration Result
- Low Brier score indicates good probability estimation.
- Model predictions are reasonably calibrated.

---

## Feature Importance
Top contributing features:
- Net Income to Stockholder’s Equity  
- Borrowing Dependency  
- Equity to Liability  

These features have the highest impact on predictions.

---

## Overfitting Discussion
- Training PR-AUC ≈ 1.0
- Validation PR-AUC ≈ 0.49–0.52
- Overfit gap ≈ 0.5

Conclusion:
- Model memorizes training data.
- Generalization is limited.
- Regularization and tuning helped reduce overfitting.

---

## AI Usage
- AI tools (ChatGPT / Codex) were used for:
  - Debugging errors
  - Structuring code and experiments
  - Generating evaluation logic
- All outputs were reviewed and validated manually.