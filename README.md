# Loan-Default-Risk-Analysis

## Objective
The primary objective of this project is to build a predictive model to estimate the risk of default on personal loans and to identify the most influential factors affecting loan default. By understanding the drivers of loan risk, we aim to provide insights into borrower behavior and enable data-driven strategies for risk mitigation.

## Data
- The dataset consists of loan records containing various features about each loan and borrower, including financial indicators, credit scores, employment length, and loan terms. 
- The data was collected between January 2015 and September 2016, and the loan_status column represents the most recent status as of January 23, 2017. This status is used as the target variable for classification.

The possible values for loan_status include:

**"Current"** – The borrower is current with all required payments.
**"Fully Paid"** – The borrower has repaid the loan in full.
**"Default"** – The borrower has missed payments, indicating a risk of default.

## Project Overview

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

### Data Splitting:

The dataset was split into training and testing sets with a 70/30 ratio to evaluate model performance on unseen data.

### Class Imbalance Handling:

Given the imbalance in loan status classes, various techniques were employed to improve the model's ability to identify defaults, including SMOTE (Synthetic Minority Over-sampling Technique), undersampling of the majority class, and setting scale_pos_weight in models like XGBoost to adjust for class imbalance.

### Model Training:

- Random Forest Classifier: Used as an initial benchmark model. This model provided insight into feature importance but struggled with class imbalance, resulting in limited recall for the default class.
- Advanced XGBoost Optimization: Implemented XGBoost with a detailed hyperparameter tuning process using GridSearchCV. Parameters such as learning rate, max depth, min child weight, gamma, and scale_pos_weight were fine-tuned to enhance performance. The final model achieved a balance between precision and recall for both classes, especially improving recall for defaults.
- Balanced Random Forest and Easy Ensemble: These models were trained to specifically address class imbalance, yielding higher recall scores for the default class, which is essential for effective default prediction.
  
### Evaluation Metrics:

- For each model, evaluation metrics including accuracy, precision, recall, and F1-score were calculated to provide a comprehensive understanding of model performance.
- A confusion matrix was generated for each model to visualize true positive, true negative, false positive, and false negative rates, with a specific focus on the model’s performance in identifying defaults (the minority class).
- Comparisons across models highlighted the trade-offs between precision and recall, guiding the selection of the final model.
  
### Feature Importance Analysis:

Feature importances from Random Forest, Balanced Random Forest, and Easy Ensemble models were analyzed to identify key predictors of loan default. This information is useful both for model interpretation and for refining future predictive models.

**Feature Importance:**

Extracted and ranked feature importances from the trained model to identify which borrower and loan characteristics are most predictive of default risk.

## Results
The model results include:

- Classification Report: Precision, recall, and F1-score metrics for model performance on identifying loan default risk.

- Confusion Matrix: Visual representation of true positive, true negative, false positive, and false negative rates.

- Feature Importance: Ranking of features by importance, revealing the primary drivers of loan default.
  
- The findings offer valuable insights into the key predictors of loan performance, enabling more informed lending decisions and enhanced risk management strategies.
