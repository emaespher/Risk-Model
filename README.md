# Risk-Model
This program differentiates between good and risky clients to make better decisions regarding credit approvals

This project aims to build a machine learning model to predict whether a customer will be more than 34 days late on their first smartphone loan within the first 77 days of origination. This helps to make more informed credit approval decisions and assign personalized interest rates based on predicted risk.

## Problem Statement

We need to distinguish between low-risk and high-risk customers requesting a credit for purchasing a smartphone. The goal is to build a predictive model that can classify new customers into good or risky.

## Datasets

- **Main Dataset**: Internal records(It includes customer applications, approval history, and internal credit behavior).
- **External Bureau Dataset**: Credit history of customers with other financial institutions (1-to-many relation by 'customer_id').

## Target Variable

`target` =  
- 1: if the customer had **x ≥ 34 days** in the first 77 days after the loan started (where x is a delay).  
- 0: otherwise.

## ⚙️ Model Selection

I selected **logistic regression** as the baseline model due to:
- Its interpretability and computational efficiency.
- The binary nature of the target variable.
- Correlation analysis showed meaningful but dispersed relationships across features.
- It allows us to compute **risk scores**, which are useful for interest rate assignment.

## Interest Rate Logic (Risk-Based Pricing)

The final interest rate could be built as:

Final Rate = TIIE + Predicted Risk Margin + Operational/Commercial Margin

This allows us to assign **personalized interest rates** based on predicted risk.

## Data Preprocessing

- Missing values handled (e.g. imputed or removed).
- Made dummies for categorical features.
- Aggregated external credit data per 'customer_id' before joining.
- Feature standarization with 'StandardScaler'.

## Evaluation

Model performance was evaluated using:
- Accuracy

## Tools & Libraries

- Python
- Pandas, NumPy
- Scikit-learn
- Seaborn, Matplotlib
  

## Future Improvements

- Test more complex models (e.g. XGBoost, Random Forests).
- Implement model monitoring with MLOps tools.
- Explore SHAP values for deeper feature importance analysis.

## Author

Emanuel Espinosa H.
