# Credit_Risk_Analysis <br />

Credit risk is an inherently __unbalanced classification__ problem , as good loans easily outnumber risky loans.  In this program we will employ different techniques to train and evaluate models with unbalanced classes.  I will use the following libraries:  **"imbalance-learn"** and **"scikit-learn"**.

From LendingClub, a peer-to-peer lending services company, we will import a credit card dataset named __"LoanStats_2019Q1.csv"__.  We will use several models to predict credit risk, and find out what are the best models for this type of data.<br />

# Part 1 - Use Resampling Models to Predict Credit Risk<br />

The goal is to evaluate three machine learning models by using resampling to determine which is better at predicting risk.  With all those 3 models we will perform the following steps: resample the dataset, view the count of the target sets, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

The dataset is unbalanced, as the dataset contains: 68,470 low_risk and 347 high_risk.  Hence the 99.5% (majority class) and 0.5% (target class).
The data train set has 51,366 "low_risk" and 246 "high_risk".  We resample the data train dataset, and created synthetic points for the low risk.  So the new dataset has 51,366 high and low risk points, being equaly balanced.  Using the LogisticRegression model we will calculate the accuracy score, a confusion matrix.<br />

# 1. RandomOverSampler<br />
**Confusion Matrix**<br />
![image alt<](/Confusion_Matrix_RandomOverSampler.PNG)
<br />
**Imbalanced Classification**<br />
![image alt <](/classification_report_RandomOverSampler.PNG)
<br />
# 2. SMOTE<br />
**Confusion Matrix**<br />
![image alt <](/Confusion_Matrix_SMOTE.PNG)<br />

**Imbalanced Classification**<br />
![image alt <](/classification_report_SMOTE.PNG)<br />

# 3. ClusterCentroids<br />

**Confusion Matrix**<br />
![image alt <](/Confusion_Matrix_UnderSampling.PNG)<br />

**Imbalanced Classification**<br />
![image alt <](/classification_report_UnderSampling.PNG)<br />

# 4. SMOOTEENN<br />

**Confusion Matrix**<br />
![image alt <](/Confusion_Matrix_SMOOTEEN.PNG)<br />

**Imbalanced Classification**<br />
![image alt <](/classification_report_UnderSampling.PNG)<br />


## Summary of all Scores by Resampling Model<br />

__Naive Random Oversampling__ (using function RandomOverSampler)<br />
![image alt <](/scores_RandomOverSampler.PNG)<br />

__SMOTE Oversampling__ (using function SMOTE)<br />
![image alt <](/scores_SMOTE.PNG)<br />

__Undersampling__ (using function ClusterCentroids)<br />
![image alt <](/scores_UnderSampling.PNG)<br />

__Combination Over and Under Sampling__ (using function SMOOTEENN)<br />
![image alt <](/scores_SMOOTEEN.PNG)<br />

Overall, the best resampling model for our specific dataste was **SMOTE**, which reported a **f-1 score of 0.81**, with an accuracy of 0.99 and a recall of 0.69.  The ranking of f-1 scores for our dataset stands: 1. SMOTE Oversampling 0.81, 2. Naïve Random OverSampling (0.78), 3. Combination Under and Over Sampling - SMOTEENN (0.74), 4. UnderSampling (0.56).
<br />
