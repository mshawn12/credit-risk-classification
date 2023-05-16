# credit-risk-classification

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* The purpose of this analysis is to use various techniques to train and evaluate a model based on loan risk to identify the creditworthiness of borrowers
* The data set contains information such as:
    * Loan Size
    * Interest Rate
    * Borrower Income
    * Debt to Income Ratio
    * Number of Accounts
    * Derogatory Marks
    * Total Debt
* The `value_counts` function was used on our y variable to determine Loan Status. A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.
* Stages of the Machine Learning Process:
    * Split the Data into Training and Testing Sets
        * Step 1: Load the data into a Pandas DataFrame
        * Step 2: Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.
        * Step 3: Check the balance of the labels variable (y) by using the `value_counts` function.
        * Step 4: Split the data into training and testing datasets by using `train_test_split`.
    * Create a Logistic Regression Model with the Original Data
        * Step 1: Fit a logistic regression model by using the training data (X_train and y_train).
        * Step 2: Save the predictions on the testing data labels by using the testing feature data (X_test) and the fitted model.
        * Step 3: Evaluate the model’s performance by doing the following:
            - Calculate the accuracy score of the model.
            - Generate a confusion matrix.
            - Print the classification report.
    * Predict a Logistic Regression Model with Resampled Training Data
        * Step 1: Use the `RandomOverSampler` module from the imbalanced-learn library to resample the data. Be sure to confirm that the labels have an equal number of data points.
        * Step 2: Use the `LogisticRegression` classifier and the resampled data to fit the model and make predictions.
        * Step 3: Evaluate the model’s performance by doing the following:
            - Calculate the accuracy score of the model.
            - Generate a confusion matrix.
            - Print the classification report.


## Results

* Machine Learning Model 1:
  * Balanced Accuracy Score: 95.20%
  * Precision:
    - 0: 100%
    - 1: 85%
  * Recall:
    - 0: 99%
    - 1: 91%
  * F-1 Score:
    - 0: 100%
    - 1: 88%



* Machine Learning Model 2:
  * Balanced Accuracy Score: 99.50%
  * Precision: 
    - 0: 100%
    - 1: 99%
  * Recall:
    - 0: 99%
    - 1: 100%
  * F-1 Score:
    - 0: 100%
    - 1: 99%

## Summary
While both logistic regression models work well, it appears that the logistic regression model fit with oversampled data performs slightly better, with higher scores in all categories (Balanced Accuracy Score, Precision, Recall, F1-Score)

As a refresher our model seeks to assign a value of `0` or `1` for Loan Status. A value of `0` in the “loan_status” column means that the loan is healthy. A value of `1` means that the loan has a high risk of defaulting.

Given that it is more important to determine credit default risk (indicated by `1`), it is recommended that Model 2 (Logistic Regression with Oversampled Data) is used as the scores are higher across all categories for `1` (Balanced Accuracy Score, Precision, Recall, F1-Score)


