# Assignment 5: Comparative Binary Classification with XGBoost

## Student Information
- **Name:** Linn Jose  
- **Student ID:** 100998224  
- **Course:** Applied Data Analytics  

---

##  Project Overview

This project builds and evaluates machine learning models to predict whether a company will go bankrupt.

The dataset is highly imbalanced (~3% bankrupt cases), making this a challenging classification problem.

---

##  Objective

- Predict bankruptcy (`Bankrupt?`)
- Focus on identifying risky companies
- Minimize false negatives (missing bankrupt companies)

---

##  Approach

The workflow includes:

1. Exploratory Data Analysis (EDA)
2. Stratified Train / Validation / Test split (70/15/15)
3. Data preprocessing
4. 5 model experiments:
   - Logistic Regression (baseline)
   - XGBoost baseline
   - XGBoost with imbalance handling
   - Tuned XGBoost
   - Reduced feature XGBoost
5. Model evaluation using:
   - PR-AUC (primary metric)
   - Brier Score (calibration)
6. Final model selection
7. Test evaluation and interpretation

---

##  Key Results

- **Final Model:** Tuned XGBoost
- **Test PR-AUC:** ~0.52  
- **Test ROC-AUC:** ~0.96  
- **Brier Score:** ~0.02  

The model shows strong discrimination ability but still misses some bankrupt cases.

---

##  Repository Structure
assignment5/
│
├── linn_assignment5.ipynb # Main notebook
├── README.md # Project description
├── requirements.txt # Dependencies
└── data.csv # Dataset

