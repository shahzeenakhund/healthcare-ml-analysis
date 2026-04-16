# healthcare-ml-analysis
Machine Learning project for diabetes prediction using EDA, SMOTE, and classification models
Diabetes Prediction Machine Learning Project

This project uses machine learning to predict diabetes using patient health data.

Workflow:
Data Cleaning & Preprocessing
Exploratory Data Analysis (EDA)
Feature Scaling
SMOTE for Class Imbalance
Logistic Regression & Random Forest Models
Model Evaluation
Models Used:
Logistic Regression
Random Forest Classifier
Results:
Logistic Regression: ~83.7% (before SMOTE), ~70.7% (after SMOTE)
Random Forest: ~78.5%
Key Insights:
Glucose is the most important feature
BMI and Age also contribute significantly
Class imbalance affects recall performance
Tools:
Python, Pandas, NumPy
Scikit-learn
Seaborn, Matplotlib
SMOTE (imbalanced-learn)

📊 Detailed Analysis Notes
📁 Dataset Overview

This study uses the Pima Indians Diabetes Dataset from the UCI Machine Learning Repository. The dataset is widely used for binary classification problems in healthcare analytics.

🔹 Features

The dataset includes the following medical attributes:

Pregnancies
Glucose concentration
Blood Pressure
Skin Thickness
Insulin level
BMI (Body Mass Index)
Diabetes Pedigree Function
Age
🔹 Target Variable
Outcome:
0 → Non-diabetic
1 → Diabetic
🧹 Data Preprocessing

During initial exploration, several features (Glucose, Blood Pressure, BMI, Insulin) contained invalid zero values, which were treated as missing data.

To handle this:

Zero values were replaced with median imputation
This preserved distribution shape while reducing bias from extreme values
⚖️ Handling Class Imbalance (SMOTE)

The dataset showed a significant class imbalance, with non-diabetic cases dominating.

To address this, SMOTE (Synthetic Minority Oversampling Technique) was applied.

🔹 Purpose of SMOTE:
Generates synthetic samples for the minority class
Balances class distribution in training data
Improves model sensitivity toward diabetic cases

This is especially important in healthcare applications where false negatives are critical.

🤖 Machine Learning Models

Two classification models were evaluated:

1. Logistic Regression

A linear probabilistic model used as a baseline classifier.

Trained on scaled and SMOTE-balanced data
Provides interpretable results
Useful for understanding feature relationships
2. Random Forest Classifier

An ensemble learning method based on multiple decision trees.

Captures non-linear relationships
More robust to noise and feature interactions
Trained on the same processed dataset
📈 Model Performance

After preprocessing (scaling + SMOTE):

Logistic Regression Accuracy: ~70.8%
Random Forest Accuracy: ~78.6%

Although Logistic Regression showed higher accuracy in its initial form, performance decreased after class balancing due to its sensitivity to data distribution changes. In contrast, Random Forest maintained more stable and reliable performance.

🔑 Feature Importance Analysis

The Random Forest model identified the following most influential predictors:

Glucose: Strongest predictor of diabetes risk
BMI: Indicator of metabolic health
Age: Known risk factor for Type 2 diabetes
Diabetes Pedigree Function: Genetic predisposition factor

These findings are consistent with established medical knowledge, increasing the model’s interpretability and credibility.

🧠 Key Insights
Class imbalance significantly impacts model evaluation, especially recall for minority class prediction
SMOTE improves minority class representation but may affect overall accuracy trade-offs
Ensemble models (Random Forest) are more robust for non-linear medical datasets
Glucose remains the most critical predictor of diabetes
⚖️ Final Conclusion

This project demonstrates a complete machine learning pipeline for diabetes prediction, including preprocessing, imbalance handling, model training, and evaluation. While Logistic Regression provides interpretability, Random Forest delivers superior predictive stability.

In healthcare contexts, improving recall for diabetic cases is more important than maximizing accuracy, as missing positive cases can have serious consequences.
