# Thyroid Cancer Recurrence ML

Machine learning project for predicting recurrence of differentiated thyroid cancer using demographic and clinicopathological features.

## Research Question

Can demographic and clinicopathological features be used to classify whether a patient with differentiated thyroid cancer will experience recurrence?

## Dataset

**Dataset:** Differentiated Thyroid Cancer Recurrence  
**Source:** UCI Machine Learning Repository  
**Dataset ID:** 915  
**DOI:** 10.24432/C5632J  
**Licence:** CC BY 4.0

The dataset contains 383 patient records, 16 input features, and one binary target variable: `Recurred`.

## Machine Learning Task

Binary classification.

## Planned Models

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting / XGBoost

## Evaluation

Model performance will be evaluated using:

- ROC-AUC
- Recall
- Precision
- F1-score
- Confusion Matrix

Stratified cross-validation will be used because the target classes are imbalanced.

## Responsible ML

This dataset is relatively small and may not represent all thyroid cancer populations. Potential data leakage, especially from post-treatment variables such as `Response`, will also be investigated.

This project is for educational purposes and should not be interpreted as a clinical decision-support system.

## Project Status

Milestone 1 — Project Proposal
