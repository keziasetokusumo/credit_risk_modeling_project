# Predicting Defaults on Personal Loans with Machine Learning Models

## Overview and problem statement
Modeling credit risk is an extremely important task for many lenders and financial institutions. Accurate credit risk assessment helps lenders evaluate potential customers and helps firms assess their portfolio's risk exposure. This project aims to use machine learning algorithms to build a model that correctly predicts if a given customer will default on their loan and identifies the most relevant features.

## The data
The file `credit_risk_dataset.csv` contains the credit history of customers who have taken a loan. Using this dataset, we will build a tool that predicts whether a given customer will default. The original dataset contains 32,581 rows and 12 columns. The columns are:
* `person_age`: Age

* `person_income`: Annual Income

* `person_home_ownership`: Home ownership

* `person_emp_length`:Employment length (in years)

* `loan_intent`: Loan intent

* `loan_grade`: Loan grade

* `loan_amnt`: Loan amount

* `loan_int_rate`: Interest rate

* `loan_status`: Loan status (0 is non-default, 1 is default)

* `loan_percent_income`: Percent income

* `cb_person_default_on_file`: Historical default

* `cb_preson_cred_hist_length`:	Credit history length

The column `loan_status` will serve as the target variable in our analysis. The target variable's unique values are 0 and 1. A value of 0 denotes non-default and a value of 1 denotes default.

## Data analysis and reproducibility
The [Jupyter Notebook](https://github.com/keziasetokusumo/credit_risk_modeling_project/blob/main/credit-analysis.ipynb) includes code that will automatically download and install the required spreadsheet and libraries for users who don't have the relevant Python libraries or datasets.
