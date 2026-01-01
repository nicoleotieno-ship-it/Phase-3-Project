# Phase-3-Project
Machine Learning Phase

# Credit Card Default Prediction Project

## Overview
This project predicts whether a customer will default on their credit card payment in the next month. The goal is to help a commercial bank’s credit risk management team proactively identify high-risk customers and take appropriate action to mitigate financial losses. This is a **classification problem** because the target variable is categorical: default (1) or no default (0).

## Business and Data Understanding
Credit card default represents a significant financial risk to banks. By predicting defaults, the bank can implement risk-based strategies, such as adjusting credit limits, offering payment plans, or enhancing monitoring of at-risk customers. 

The dataset used is the **UCI Credit Card Default dataset** from Kaggle, containing 30,000 records and 25 columns. It includes demographic features (e.g., `SEX`, `EDUCATION`, `MARRIAGE`, `AGE`), credit and billing information (e.g., `LIMIT_BAL`, `BILL_AMT1–6`), payment history (`PAY_0–6`), and past payments (`PAY_AMT1–6`). The target variable is `default.payment.next.month` (renamed to `default` in this project).

The dataset is imbalanced, with fewer customers defaulting than not, reflecting real-world financial scenarios. This informed the choice of evaluation metrics, prioritizing **recall** to minimize the risk of missing actual defaulters.

## Stakeholder
Primary stakeholder: **Credit Risk Management Team** of a commercial bank.  
Objective: Use model predictions to mitigate financial risk by identifying high-risk credit card customers before default occurs.

## Modeling
Three main models were developed iteratively:

1. **Baseline Logistic Regression** – simple and interpretable, provides a starting point for evaluation.
2. **Tuned Logistic Regression** – applied class weighting to handle imbalance, optimizing recall for defaulters.
3. **Random Forest Classifier** – non-parametric ensemble model, captures complex patterns and interactions.

**Final Model Selection:**  
The tuned logistic regression model was selected as the final model due to its **highest recall**, interpretability, and ease of deployment. Random Forest was retained for comparison and feature importance insights.

## Evaluation
Evaluation focused on **classification metrics**:

- **Recall:** Primary metric; high recall reduces the risk of missing customers likely to default.
- **Precision, F1-score, Accuracy:** Additional metrics for overall model performance.

The tuned logistic regression model achieved the best balance between **recall and interpretability**, making it the most suitable for business deployment.

## Limitations
- **Class Imbalance:** Despite tuning, the dataset contains fewer defaults, which may lead to missed defaulters.
- **False Negatives:** Some risky customers may still be misclassified.
- **Feature Scope:** Only historical payment and demographic data are included; behavioral or external financial data could improve predictions.
- **Model Complexity:** Random Forest captures complex patterns but is harder to interpret for stakeholders.
- **Temporal Limitations:** The dataset is static; customer behavior changes over time, requiring retraining.

## Recommendations / Next Steps
- Implement the tuned logistic regression model in production for proactive risk monitoring.
- Continue collecting additional behavioral and financial features to enhance predictive performance.
- Periodically retrain models to capture evolving customer behavior.
- Explore ensemble methods (e.g., combining logistic regression and Random Forest) to improve prediction robustness.
- Monitor false negatives and refine thresholds to balance recall and precision based on business objectives.

## Conclusion
This project demonstrates an end-to-end approach to solving a **predictive classification problem** in finance. By combining multiple models, iterative evaluation, and proper handling of imbalanced data, the final tuned logistic regression model provides actionable insights to stakeholders while maintaining interpretability and business relevance.
