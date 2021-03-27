# Credit_Risk_Analysis

Credit risk is an inherently __unbalanced classification__ problem , as good loans easily outnumber risky loans.  In this program we will employ different techniques to train and evaluate models with unbalanced classes.  I will use the following libraries:  **"imbalance-learn"** and **"scikit-learn"**.

From LendingClub, a peer-to-peer lending services company, we will import a credit card dataset named __"LoanStats_2019Q1.csv"__.  We will use several models to predict credit risk, and find out what are the best models for this type of data.

# Part 1 - Use Resampling Models to Predict Credit Risk

The goal is to evaluate three machine learning models by using resampling to determine which is better at predicting risk.  With all those 3 models we will perform the following steps: resample the dataset, view the count of the target sets, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

The dataset is unbalanced, as the dataset contains: 68,470 low_risk and 347 high_risk.  Hence the 99.5% (majority class) and 0.5% (target class).

1. RandomOverSampler6
2. SMOTE
3. ClusterCentroids

## 1. RandomOverSampler

The data train set has 51,366 "low_risk" and 246 "high_risk".  We resample the data train dataset, and created synthetic points for the low risk.  So the new dataset has 51,366 high and low risk points, being equaly balanced.  Using the LogisticRegression model we will calculate the accuracy score, a confusion matrix

## Summary of all Scores by Resampling Model
### Naive Random Oversampling (using function RandomOverSampler)
![](/scores_RandomOverSampler.PNG)
### SMOTE Oversampling (using function SMOTE)
![](/scores_SMOTE.PNG)
### Undersampling (using function ClusterCentroids)
![](/scores_UnderSampling.PNG)
### Combination Over and Under Sampling (using function SMOOTEEN)
![](/scores_SMOOTEEN.PNG)
