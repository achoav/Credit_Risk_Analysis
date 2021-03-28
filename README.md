# Credit_Risk_Analysis <br />

Credit risk is an inherently __unbalanced classification__ problem , as good loans easily outnumber risky loans.  In this program we will employ different techniques to train and evaluate models with unbalanced classes.  I will use the following libraries:  **"imbalance-learn"** and **"scikit-learn"**.

From LendingClub, a peer-to-peer lending services company, we will import a credit card dataset named __"LoanStats_2019Q1.csv"__.  We will use several models to predict credit risk, and find out what are the best models for this type of data.<br />

# Part 1 and 2 - Use Resampling Models to Predict Credit Risk<br />

The goal is to evaluate three machine learning models by using resampling to determine which is better at predicting risk.  With all those 3 models we will perform the following steps: resample the dataset, view the count of the target sets, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

The dataset is unbalanced, as the dataset contains: 68,470 low_risk and 347 high_risk.  Hence the 99.5% (majority class) and 0.5% (target class).
The data train set has 51,366 "low_risk" and 246 "high_risk".  We resample the data train dataset, and created synthetic points for the low risk.  So the new dataset has 51,366 high and low risk points, being equaly balanced.  Using the LogisticRegression model we will calculate the accuracy score, a confusion matrix.<br />

# 1. RandomOverSampler<br />
**Confusion Matrix**<br />
![image alt<](/Confusion_RandomOverSampler.PNG)
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

**Confusion Matrix**
<br />
![image alt <](/Confusion_Matrix_UnderSampling.PNG)<br />

**Imbalanced Classification**<br />
![image alt <](/classification_report_UnderSampling.PNG)<br />

# 4. SMOOTEENN<br />

**Confusion Matrix**<br />
![image alt <](/Confusion_Matrix_SMOOTEEN.PNG)<br />

**Imbalanced Classification**<br />
![image alt <](/classification_report_UnderSampling.PNG)<br />


# Part 3 and 4 - Use Ensemble Classifiers to Predict Credit Risk<br />

Using both algorithms: Balance Random Forest Classifier and Easy Ensemble Classifier, I will resample the dataset, view the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

## 5. Balanced Random Forest Classifier
- An accuracy score for the model is calculated: 
- A confusion matrix has been generated
- An imbalanced classification report has been generated
- The features are sorted in descending order by feature importance

![image_alt<](/Random_Forest_Confusion_Matrix.PNG)
<br />  
![image_alt<](/classification_report_Random.PNG)
<br />  
![](/Random_Features.PNG)
<br />  
## 6. Easy Ensemble AdaBoost Classifier
- An accuracy score of the model is calculated
- A confusion matrix has been generated
- An imbalanced classification report has been generated
<br />  
![image alt <](/EEC_Confusion_Matrix.PNG)
<br />  
![](/classification_report_EEC.PNG)
<br />

# Summary

Overall, the best resampling model for our specific database was **SMOTE**, which reported a **f-1 score of 0.81**, with an accuracy of 0.66 and a recall of 0.63 for High Risk loans.  The best ensemble learner model for our specific database was **Easy Ensemble AdaBoost Classifier**, with an accuracy of 0.92 and a recall of 0.91 for High Risk loans.

However, we want to find the best model for our specific dataset, so we will rank them on f-1 scores, recall rate for High Risk loans, recall rate for Low Risk loans, and accuracy:

## The ranking of f-1 scores for our dataset stands: 
1. Easy Ensemble AdaBoostClassifying (0.97)
2. Balanced Random Forest Classifier (0.95)
3. SMOTE Oversampling (0.81) 
4. Naïve Random OverSampling (0.78)
5. SMOTEENN Over and Under Sampling (0.72)
<br />

## The ranking of recall rate for High Risk loans:
This analysis is trying to find the best model that can detect if a loan is high risk or not. Becasue of that, we need to find a model that lets the least amount of high risk loans pass through undetected. That correlating statistic for this is the **recall rate** for **High Risk**. Looking through the different models, the ones that scored the highest were:
1. Easy Ensemble AdaBoost Classifying (0.91)
2. SMOTEENN Over and Under Sampling (0.79)
3. Naive Random Oversampling (0.69)
4. Balanced Random Forest Classifier (0.67)
5. SMOTE Oversampling (0.63)
<br />

## The ranking of recall rate for Low Risk loans:
While the recall rate for High Risk loans is the most important statistic that is pulled from this analysis, another important statistic is **recall rate** for **low risk** as it shows how many low risk loans are flagged as high risk. Looking through the different models, the ones that scored the highest were:
<br />
1. Easy Ensemble AdaBoost Classifying (0.94)
2. Balanced Random Forest Classifying (0.91)
3. SMOTE Oversampling (0.69)
4. Naive Random Oversampling (0.64)
5. SMOTEENN Over and Under Sampling (0.56)
<br />

## The ranking of accuracy:
After taking these two statistics over the others, we can look at the accurary score to get a picture of how well the model performs in general. The models with the highest **accuracy scores** were:
<br />
1. Easy Ensemble AdaBoost Classify (0.925)
2. Balanced Random Forest Classifying (0.788)
3. SMOTEENN Over and Under Sampling (0.678)
4. Naive Random Oversampling (0.669)
5. SMOTE Oversampling (0.663)
<br />

After factoring in these main statistics, the model that I would recommend to use for predicting high risk loans is the Easy Ensemble AdaBoost Classifying model followed by Balanced Random Forest Classifying.

This can also be visually seen on the following Precision Recall Graph comparison:
<br />
![image alt <](/ensemble.PNG)<br />

