Fraud Risk Portfolio Model

Interpretable Fraud Detection using XGBoost and SHAP

📌 Project Overview

This project develops an interpretable fraud detection system using gradient boosting (XGBoost) combined with SHAP explainability.

The objective is to:

Detect fraudulent transactions

Understand key portfolio-level fraud drivers

Analyze behavioral and structural fraud signals

Provide explainable risk segmentation

The model integrates anomaly detection (via PCA features) with engineered behavioral features to simulate a production-aligned fraud risk engine.

📊 Dataset Description

The dataset contains anonymized transaction features including:

PCA-transformed components (V1–V28)

Transaction Amount

Timestamp information

Fraud label (binary classification)

The PCA components represent latent transaction structure and behavioral signatures.

🔧 Data Science Pipeline
1️⃣ Data Cleaning

Verified missing values

Checked class imbalance

Prevented data leakage

Extracted time-based features from timestamp

2️⃣ Preprocessing

Applied SMOTE to handle severe class imbalance

Log transformation applied to transaction amount

Feature normalization handled implicitly via PCA structure

3️⃣ Feature Engineering

Created behavioral fraud indicators:

Amount_log – log-transformed transaction amount

Amount_Deviation – deviation from baseline transaction behavior

Hour – extracted from transaction timestamp

Night_Transaction – binary indicator for off-hour risk

These features introduce behavioral intelligence beyond structural anomaly detection.

🤖 Model Development

Model used:

XGBoost Classifier

200 estimators

Max depth: 5

Learning rate: 0.1

Evaluation metric: Log Loss

Why XGBoost?

Handles non-linear relationships

Strong performance on imbalanced datasets

Robust to multicollinearity

Industry-standard for fraud detection

📈 Model Performance

The model demonstrates strong fraud discrimination capability using:

ROC-AUC

Confusion Matrix

Risk score segmentation

Fraud concentration increases significantly within upper risk score buckets, validating predictive stability.

🔍 Model Interpretability (SHAP Analysis)

SHAP analysis was used to quantify feature contribution at both global and local levels.

Key Global Fraud Drivers:

V14 (dominant latent anomaly component)

V4

V12

Hour (temporal risk)

Amount_log

Amount_Deviation

Insights:

Fraud risk is strongly driven by latent structural anomalies.

Transaction timing significantly impacts fraud probability.

Behavioral spending deviation materially increases risk.

The model captures multi-dimensional fraud patterns rather than rule-based triggers.

📊 Portfolio Risk Interpretation

Fraud within the portfolio appears to be driven by:

Structural transaction anomalies

Time-of-day risk exposure

Abnormal transaction magnitude relative to user behavior

Risk signals are distributed across multiple features, reducing dependency on any single variable and increasing model robustness.

🧠 Business Implications

Enables dynamic risk-based transaction monitoring

Supports explainable AI compliance requirements

Allows adaptive fraud thresholding by time-of-day

Strengthens behavioral anomaly detection

🛠 Technologies Used

Python

Pandas / NumPy

Scikit-learn

XGBoost

SHAP

Matplotlib / Seaborn
