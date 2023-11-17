# Predicting Defaults on Personal Loans with Machine Learning Models
![cardmapr-nl-XH2JFgT4Abc-unsplash](https://github.com/keziasetokusumo/credit_risk_modeling_project/assets/111642763/938a16c0-5990-40d9-ad40-cb9e3bc4caa6)

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

The column `loan_status` will serve as the target variable in our analysis. The unique values of the target variable are 0 and 1. A value of 0 denotes non-default, and 1 means default.

The original dataset isn't evenly distributed, as we have more information for 'no default' customers than 'default':

<img width="396" alt="Screen Shot 2023-11-17 at 7 50 13 AM" src="https://github.com/keziasetokusumo/credit_risk_modeling_project/assets/111642763/cfc97871-4e4e-42c8-b30b-9eff252bc2de">

We deal with this issue later in our analysis while testing different algorithms.

## Data analysis and reproducibility
The [Jupyter Notebook](https://github.com/keziasetokusumo/credit_risk_modeling_project/blob/main/credit-analysis.ipynb) includes code that will automatically download and install the required spreadsheet and libraries for users who don't have the relevant Python libraries or datasets.

## Method
This project deals with a classification problem, as we're building a model to predict if a customer defaults. We start by preprocessing and cleaning the original dataset, and the procedure consists of:

* Filling null values
* Assigning numerical values to categorical columns
* Removing highly correlated predictor variables
* Resampling to address unequal data distribution
  
Once the data has been handled, we tested with different algorithms:
* Logistic regression
* K-neighbors
* Random forest
* XGBoost
  
After evaluating these models against performance metrics, we identify the most optimal model for predicting loan defaults. Finally, we use the chosen model to identify the most essential features in this classification problem.

## Results
Running and testing different algorithms, we found that our hyper-tuned XGBoost model is ideal for this classification task. A summary table containing performance metrics of all the models we've fitted is shown below:

<img width="345" alt="Screen Shot 2023-11-17 at 7 52 20 AM" src="https://github.com/keziasetokusumo/credit_risk_modeling_project/assets/111642763/0d6f3210-5cef-4143-bfc2-17bc77892c53">

The XGBoost model returns the best scores. XGBoost is a tree-boosting model that sequentially generates several decision trees, and each new tree is improved with the mistakes made by the previous one. The optimal XGBoost model has the following parameters:

`xgb.XGBClassifier(eta=0.8, booster='dart', alpha=0.01)`

Since we have many predictor variables (22 columns after data processing), we generated a bar graph that plots the corresponding F-score against the columns we used in our analysis and limited the number of features to 10. F-score relates to the frequency with which the model uses a given independent variable to split a tree. The higher the F-score, the more relevant the feature is. Our top 10 predictor variables are shown below:

<img width="345" alt="Screen Shot 2023-11-17 at 7 52 20 AM" src="https://github.com/keziasetokusumo/credit_risk_modeling_project/assets/111642763/8bd1911a-31ee-4329-afaa-4dc1e96367d1">

