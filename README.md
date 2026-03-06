# Credit Card Fraud Detection. Financial Machine Learning Project

## Overview

Credit card fraud represents a major financial risk for banks and fintech companies.  
This project develops a machine learning pipeline to detect fraudulent transactions using anonymized credit card data.

The objective is to identify fraud while minimizing false positives and estimating the potential financial impact of the model.

---

## Dataset

This project uses the **Credit Card Fraud Detection dataset** available on Kaggle.

- Total transactions: **284,807**
- Fraud cases: **492**
- Fraud rate: **~0.17%**
- Total fraud volume: **~$60,000**

Features **V1–V28** are PCA-transformed variables to protect customer privacy.

Due to Kaggle data policies and GitHub file size limits, the dataset is **not included in this repository**.

You can download it here:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Place the dataset in: data/raw/creditcard.csv


## 📂 Project Structure

```text
credit-card-fraud-detection/
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_model_training.ipynb
│   ├── 04_model_explainability.ipynb
│   └── 05_business_impact.ipynb
└── models/
    └── xgboost_fraud_model.pkl

requirements.txt
README.md


---
```
## Machine Learning Models

The following models were evaluated:

- Logistic Regression
- Random Forest
- XGBoost

### Best Model

**XGBoost** achieved the best performance.

Key metrics:

- ROC AUC ≈ **0.97**
- Fraud Recall ≈ **0.84**

This indicates that the model detects most fraudulent transactions while maintaining strong overall predictive performance.

---

## Model Explainability

To better understand model behavior, **SHAP (SHapley Additive Explanations)** was used.

Important fraud indicators include:

- V12
- V10
- V11
- V14

These PCA components capture abnormal transaction patterns associated with fraud.

---

## Fraud Risk Score

Model probabilities were converted into a **Fraud Risk Score (0–1000)** similar to scoring systems used by financial institutions.

Interpretation:

| Score | Risk Level |
|------|-----------|
| 900–1000 | Low Risk |
| 700–900 | Medium Risk |
| 0–700 | High Risk |

This allows the system to flag suspicious transactions for manual review.

---

## Business Impact

The dataset contains approximately **$60,000 in fraudulent transactions**.

Based on model recall, the system could potentially prevent a significant portion of these losses by detecting fraud before transaction completion.

---

## Skills Demonstrated

This project demonstrates key skills relevant to financial data science:

- Financial fraud detection
- Machine learning modeling
- Handling imbalanced datasets
- Model explainability (SHAP)
- Risk scoring systems
- Business impact analysis

---

## Technologies Used

- Python
- Pandas
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib / Seaborn
- Jupyter Notebook

---

## Author

Juan Pablo Dávila  
Systems Engineering 
