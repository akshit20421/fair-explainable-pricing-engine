# 🧠 Fair Pricing Engine  
### Explainable, Calibrated & Fair Insurance Premium Modeling

---

## 📌 Overview

This project develops an end-to-end machine learning pricing system for health insurance premium estimation.

Unlike typical prediction-focused ML projects, this system integrates:

- Statistical baseline modeling (Gamma GLM)
- Advanced gradient boosting (XGBoost)
- Calibration validation
- Model explainability (SHAP)
- Fairness auditing across protected groups

The objective is not just predictive accuracy, but responsible, interpretable, and governance-aware model deployment.

---

## 📂 Project Structure

notebooks/
│
├── 01_eda.ipynb
├── 02_modeling.ipynb
└── 03_explainability_fairness.ipynb

yaml
Copy code

---

## 1️⃣ Exploratory Data Analysis

The EDA notebook focuses strictly on validating modeling assumptions.

Key steps:

- Dataset structure and feature categorization  
- Missing value analysis  
- Target variable skew analysis  
- Log-transformation justification  
- Distributional assessment of medical charges  

Findings confirm that medical charges are strictly positive, right-skewed, and heteroscedastic — supporting the use of Gamma GLM with log link as a baseline pricing model.

---

## 2️⃣ Model Development & Benchmarking

### 🔹 Baseline Model — Gamma GLM

- Log-linked Gamma regression  
- Interpretable multiplicative effects  
- Global and decile-level calibration validation  

The GLM provides a stable and interpretable benchmark pricing model.

---

### 🔹 XGBoost (Baseline Feature Set)

Using identical features as GLM, XGBoost delivers only marginal improvement in RMSE, demonstrating diminishing returns from additional model complexity.

---

### 🔹 Advanced XGBoost (Enriched Features)

Additional features included:

- Medical history  
- Family medical history  
- Exercise frequency  
- Occupation  

Results:

- Significant reduction in RMSE and MAE compared to baseline GLM  
- ~40% RMSE reduction on identical test split  
- Maintained strong decile-level calibration  

This demonstrates the ability of non-linear models to capture complex risk interactions.

---

## 3️⃣ Model Explainability (SHAP)

To ensure transparency:

- Global SHAP summary plot identifies dominant risk drivers  
- Local SHAP explanations illustrate individual premium decomposition  

Key drivers include:

- Smoking status  
- Cardiovascular medical history  
- BMI  
- Age  
- Lifestyle variables  

This confirms domain-consistent and interpretable model behavior.

---

## 4️⃣ Fairness Audit

Sensitive attribute (gender) was excluded from model training.

Post-hoc evaluation included:

- Outcome parity analysis  
- Error parity (mean and absolute error)  
- Error distribution comparison  

Findings indicate:

- No systematic overpricing of either group  
- Comparable prediction error distribution  
- No meaningful disparate impact under this evaluation framework  

---

## 📊 Key Highlights

- End-to-end ML lifecycle implementation  
- Calibration-driven validation  
- Model benchmarking with justified complexity  
- Transparent feature attribution  
- Responsible AI evaluation  

---

## 🛠️ Technologies Used

- Python  
- Pandas / NumPy  
- Statsmodels (Gamma GLM)  
- XGBoost  
- SHAP  
- Scikit-learn  
- Matplotlib / Seaborn  

---

## 🎯 Future Enhancements

- FastAPI deployment layer for real-time premium estimation  
- Lightweight web interface  
- Model artifact persistence and monitoring  
- Formal fairness statistical testing  

---

## 👤 Author

Akshit Gupta  

---

## 📌 Summary

This project emphasizes:

Performance + Calibration + Explainability + Fairness

rather than predictive accuracy alone. It reflects a production-oriented approach to machine learning in pricing sys
