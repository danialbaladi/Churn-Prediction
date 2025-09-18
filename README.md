# Telco Customer Churn Prediction

## Project Overview

Predicting customer churn is crucial for telecom companies to retain valuable customers. This project uses machine learning to identify customers likely to leave based on their demographics, service subscriptions, and billing information.

## Dataset

* **Source:** Kaggle – Telco Customer Churn
* **Rows:** 7043 | **Columns:** 21 (expanded to 30 after feature engineering)
* **Target:** `Churn` (Yes/No)

## Preprocessing & Feature Engineering

* Cleaned missing and inconsistent data.
* Converted categorical variables to numeric using encoding.
* Standardized numerical features for modeling.
* Added new features:

  * Average monthly charges (`AvgChargesPerMonth`)
  * Charge differences (`ChargeDiff`, `ChargeDiffPerc`)
  * Number of subscribed services (`NumServices`, `HasInternet`)
  * Tenure groups (`tenure_group`)
* Removed data leakage features (e.g., `ChurnFlag`).

## Modeling & Evaluation

* **Models:** Logistic Regression, Decision Tree, Naive Bayes

* **Best Model:** Logistic Regression

* **Validation Accuracy:**

  * Logistic Regression: 0.805
  * Decision Tree: 0.736
  * Naive Bayes: 0.707

* **Test Performance (Logistic Regression):**

  * Accuracy: 0.789
  * F1-Score: 0.609
  * ROC-AUC: 0.735

* Logistic Regression showed better generalization and stability in cross-validation.

## Hyperparameter Tuning

* **Logistic Regression:** `C=0.001`, `solver='liblinear'`, `max_iter=100`
* **Decision Tree:** `criterion='entropy'`, `max_depth=3`, `min_samples_leaf=1`

## Key Takeaways

* Logistic Regression outperforms Decision Tree in generalization.
* Feature engineering improves model interpretability and performance.
* Pipeline allows reproducibility and can be used for production or further experimentation.

