# Loan Analysis with Oversampling

## Overview of the Analysis

In this exercise we received information on 77,536 loans. Each loan included 8 data points: loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks, total_debt, loan_status. The dependent variable is loan_status that takes the value of ‘0’ when the loan is healthy and ‘1’ when it is a high-risk loan. The other variables are the independent variables. 

We want to create a model that can predict whether a loan is healthy or high-risk based on the independent variables. 
The dataset is imbalanced. There are a lot fewer high-risk loans (3%) than healthy loans (97%). This makes sense as banks do everything they can to avoid originating high-risk loans. 

As a first step we divided the data into training and testing using the train_test_split method from sklearn. 

**Model 1** is a logistic regression using the training data. 

**Model 2** is a logistic regression using resampled data for training. Given the imbalance in the dataset we used the RandomOverSampler method from imblearn to increase the number of high-risk loans in the training dataset. After applying that method the data is balanced i.e. it has the same number of healthy and high-risk loans (56,268). 


## Results

* Machine Learning Model 1 (original data):

Accuracy score = 0.9925

<p align='center'> <img src='images/original.jpg'></p>

* Machine Learning Model 2 (resampled data):

Balanced accuracy score: 0.9959

<p align='center'> <img src='images/resampled.jpg'></p>

## Summary

With the resampling of the data the model became better at identifing high-risk loans. The recall for '1' increased from 93% in the original model to 100% in the resampled model. The resampled model predicts more '1's and as a consequence has more false positives. 

I would recommend to use the resampled model as it has better recall while having the same precision. 

