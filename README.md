# Loan-Default-Risk-Analysis
# Objective
The primary objective of this project is to build a predictive model to estimate the risk of default on personal loans and to identify the most influential factors affecting loan default. By understanding the drivers of loan risk, we aim to provide insights into borrower behavior and enable data-driven strategies for risk mitigation.

# Data
The dataset consists of loan records containing various features about each loan and borrower, including financial indicators, credit scores, employment length, and loan terms. The data was collected between January 2015 and September 2016, and the loan_status column represents the most recent status as of January 23, 2017. This status is used as the target variable for classification.

The possible values for loan_status include:

**"Current"** – The borrower is current with all required payments.
**"Fully Paid"** – The borrower has repaid the loan in full.
**"Default"** – The borrower has missed payments, indicating a risk of default.

**Project Overview**

**Exploratory Data Analysis (EDA):**

Examined the distribution of key features, such as loan amounts, terms, installment payments, and credit scores.
Visualized the distribution of loan status categories to understand the class balance.

**Data Cleaning:**

Handled missing values in numerical columns using mean imputation.
Processed categorical features, converting strings to numeric codes or dummy variables for model compatibility.
Extracted numerical information from term (e.g., "36 months" → 36) and standardized emp_length to numeric values.

**Feature Engineering:**

Converted categorical employment length to a numerical scale, allowing it to contribute meaningfully to model predictions.
Encoded target variable loan_status to a binary format: 1 for "Default" and 0 for other statuses.

**Modeling Approach:**

Split the dataset into training and testing sets (70/30 split) to evaluate model performance.
Trained a Random Forest Classifier on the processed dataset to classify loan status based on borrower information.
Generated model evaluation metrics, including a confusion matrix and classification report, to assess predictive accuracy.

**Feature Importance:**

Extracted and ranked feature importances from the trained model to identify which borrower and loan characteristics are most predictive of default risk.

**Results**
The model results include:

Classification Report: Precision, recall, and F1-score metrics for model performance on identifying loan default risk.

Confusion Matrix: Visual representation of true positive, true negative, false positive, and false negative rates.

Feature Importance: Ranking of features by importance, revealing the primary drivers of loan default.

**Conclusion**
This project provides a comprehensive analysis of loan default risk, utilizing a robust classification model and feature importance analysis. The findings offer valuable insights into the key predictors of loan performance, enabling more informed lending decisions and enhanced risk management strategies.
