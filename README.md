# Credit_Risk_Analysis

## Overview of the Analysis
The purpose of this analysis is to employ different techniques to train and evaluate models with unbalanced classes to predict credit risk. We will be using a credit card credit dataset from LendingClub, a peer-to-peer lending services company for this analysis.

## Results
In this analysis, we will evaluate the balanced accuracy score, precision, and recall scores for the following models: 

**RandomOverSampler**
* Precision and recall are high for the majority class, but the precision is low for the minority class. Meaning that of 100 people who were classified as high risk, only one was truly high risk, and 99 were falsely identified. The f1 score is also low and is explained by the profound imbalance between the precision and recall for high risk. The balanced accuracy score is 65%. 
<img width="861" alt="NRO_classification_report" src="https://user-images.githubusercontent.com/91927712/155659199-23a4d775-7cb6-46c4-838d-3ae88dd85eeb.png">

**SMOTE** 
* The precision and recall results are the same as the Random Over Sampler Model, but the accuracy decreased to 63% in this model. The recall slightly decreased for the high risk group, and the f1 stayed the same. The balanced accuracy score is 63%.
<img width="863" alt="SMOTE_classification_report" src="https://user-images.githubusercontent.com/91927712/155659234-fd47b7b3-8be0-42cb-80b0-6512429058ab.png">

**ClusterCentroids**
* The precision for the high risk group stayed the same as previous models, but the recall for the low risk group decreased significantly which caused a decrease in its f1 score as well. The balanced accuracy score is 44%.
<img width="848" alt="Cluster_classification_report" src="https://user-images.githubusercontent.com/91927712/155659278-2fe1f662-3913-4227-82e3-f2199663f7b8.png">

**SMOTEENN**
* There was a significant increase in the recall for both groups which improved the f1 score for the low risk group. There is such a big imbalance between the precision and recall of the high risk group, which is why we aren't seeing an improvement in the f1 score even with the improvement in the recall score. The balanced accuracy score is 54%.
<img width="856" alt="SOTEENN_classification_report" src="https://user-images.githubusercontent.com/91927712/155659310-9475acf1-0da4-42df-b73d-2817b731b40b.png">


**BalancedRandomForestClassifier**
* The precision finally increased for the high risk group, which also increased the f1 score. The recall increased for both groups, putting the recall for the low risk group at 0.91 and a resulting f1 score of 0.95. The balanced accuracy score is 79%.
<img width="930" alt="BRF_classification_report" src="https://user-images.githubusercontent.com/91927712/155664665-32e3b6b9-4783-4b73-a66e-5badbceca8bd.png">

**EasyEnsembleClassifier**
* The precision and recall scores for the high risk group significantly increased, putting the recall score at 0.91. The recall score increased in the low risk group bringing it to 0.94. The balanced accuracy score is 94%.
<img width="852" alt="EE_classification_report" src="https://user-images.githubusercontent.com/91927712/155667896-55a4582b-ea68-4664-89a8-b425eaae000b.png">

## Summary
In conclusion, although we saw a gradual increase in effectiveness from model to model, even the best model, EasyEnsembleClassifier, still does a poor job at misclassifying credit risk as positive for the high risk group. For that reason, I wouldn't recommend any of the models for use until further improvements are made to reduce bias in the high risk group classifications. 
