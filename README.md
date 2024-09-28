## Project Overview
In today’s competitive banking environment, retaining customers is a significant challenge. This project is focused on predicting customer churn using historical customer data. By identifying the key factors that drive churn, banks can take preventative measures to reduce churn rates and improve customer retention.

The project utilizes machine learning models to classify customers who are likely to leave the bank based on their account and personal details. Techniques like SHAP (SHapley Additive exPlanations) and Partial Dependence Plots (PDP) are used to interpret the model and make data-driven decisions.

# Dataset
The dataset used for this project contains information about customers such as:

* Customer ID: Unique identifier for each customer.
* Credit Score: Customer's credit score.
* Geography: Country of the customer (e.g., France, Germany, Spain).
* Gender: Male or Female.
* Age: Age of the customer.
* Tenure: Number of years the customer has been with the bank.
* Balance: Account balance of the customer.
* Number of Products: Number of bank products the customer is using.
* Has Credit Card: Whether the customer has a credit card (1 = Yes, 0 = No).
* Is Active Member: Whether the customer is an active member (1 = Yes, 0 = No).
* Estimated Salary: Estimated yearly salary of the customer.
* Exited: Whether the customer has churned (1 = Yes, 0 = No).
# Features

The project analyzes the following features to predict churn:

* Customer Demographics:
Age, Gender, Geography, Estimated Salary, etc.
* Customer Account Information:
Balance, Number of Products, Credit Card usage, etc.
* Customer Activity:
Tenure, Active Membership status, etc.
The goal is to determine which features most significantly impact customer churn and use this information for predictive modeling.

## Modeling Approach
1. Data Preprocessing
Handled missing values, if any.
Categorical variables (like Geography and Gender) were encoded using one-hot encoding.
Standardized the numerical variables (e.g., balance, credit score) to ensure uniform scaling.
2. Feature Engineering
Created a new feature balance_to_salary_ratio (balance divided by estimated salary) to help distinguish between customers who maintain a high balance relative to their income.
3. Machine Learning Models
Several machine learning models were tested:

* Logistic Regression: For a baseline understanding of the problem.
* Random Forest: A robust ensemble learning method used for improved prediction accuracy.
* Extra Trees Classifier: An ensemble model that is particularly useful for analyzing feature importance.
The best model was selected based on metrics such as accuracy, precision, recall, and F1-score.

## Model Interpretation
SHAP Summary Plot
A SHAP summary plot was used to interpret feature importance. The plot shows how each feature contributes to the model’s predictions (whether a customer will churn or not). Below is an explanation of some key insights from the SHAP plot:

1. Number of Products: Customers with fewer products are more likely to churn, as indicated by the significant SHAP values.
2. Balance: Customers with lower balances tend to have a higher likelihood of leaving.
3. Active Membership: Active members have a lower likelihood of churning, while inactive members are at higher risk.

Partial Dependence Plot (PDP)
The Partial Dependence Plot shows the effect of specific features on churn probability, holding all other features constant. Here’s what the PDP results indicate:

Age: Younger customers have a higher likelihood of churning.
Balance-to-Salary Ratio: The likelihood of churn decreases as the balance-to-salary ratio increases.

## Results
### Training Performance:

1. ROC AUC: 1.0 (Perfect classification performance on the training set)
2. Precision: 1.0 (Perfect precision on the training set)
### Holdout Performance:

1. ROC AUC: 0.973 (Indicating the model is highly effective in distinguishing between churned and non-churned customers)
2. Precision: 0.926 (92.6% of the customers predicted to churn actually churned)
