# Credit Risk Analysis
Module 17 Challenge
## Overview of Analysis
We have been asked to use supervised machine learning to analyze credit card risk to classify loans as either high risk or low risk. We will be using a dataset from LendingClub to oversample and undersample the data (and use a combination approach), to get a better picture of the credit risk to make predictions. We'll compare the results from two learning models to predict the risk. 

accuracy score = 1 equals 100% predicted correctly
confusion matrix is precision, likelihood of accuracy/how reliable positive classification is, low precision = high number of false positives
recall is sensitivity how likely itll be detected, ability of the classifier to find all positive samples, low recall=large number of false negatives
high sensitivity is more important in this case, fewer false negatives better to get it wrong than go undetected, dont want to lose money, f1 score harmonic mean single summary statistic, pronounced imbalance between sensitivity and precision is low f1 score
"this model may not be the beset because the accuracy, 0.552 is low and the precision/recall are not good enough to state that the model will be good at detecting credit risk."
"the precision (confusinon matrix) is low, indicating an unreliable positive classification, recall is also low meaning large number of false negatives"

## Results -- Resampling Models

### RandomOverSampler (Oversampling) Results:
  ![randomoversampler.png](https://raw.githubusercontent.com/LaurenDebes/Credit_Risk_Analysis/main/randomoversampler.png)
  - <b>Balanced Accuracy Score:</b> 79% predicted correctly
  - <b>Precision Score:</b> Only 2% in precision, indicating a low likelihood of accuracy and a high number of false positives (low risk classifications)
  - <b>Recall Score:</b> Sensitivity score of 71% for high risk loans
  - <b>Summary:</b> This model may not be the best because the precision/recall are not good enough to state that the model will be good at predicting risk. There is a low f1 score.

### SMOTE (Oversampling) Results:
  ![SMOTE.png](https://raw.githubusercontent.com/LaurenDebes/Credit_Risk_Analysis/main/SMOTE.png)
  - <b>Balanced Accuracy Score:</b> 80% predicted correctly
  - <b>Precision Score:</b> Only 3% in precision, indicating a low likelihood of accuracy and a high number of false positives (low risk classifications)
  - <b>Recall Score:</b> Sensitivity score of 71% for high risk loans
  - <b>Summary:</b> This model may not be the best because the precision/recall are not good enough to state that the model will be good at predicting risk. There is a low f1 score.
  
### ClusterCentroids (Undersampling) Results:
  ![clustercentroids.png](https://raw.githubusercontent.com/LaurenDebes/Credit_Risk_Analysis/main/clustercentroids.png)
  - <b>Balanced Accuracy Score:</b>77% predicted correctly
  - <b>Precision Score:</b> Only 2% in precision, indicating a low likelihood of accuracy and a high number of false positives (low risk classifications)
  - <b>Recall Score:</b> Sensitivity score of 78% for high risk loans
  - <b>Summary:</b> This model may not be the best because the precision/recall are not good enough to state that the model will be good at predicting risk. There is a low f1 score.

### SMOTEENN (Combination Over/UnderSampling) Results:
  ![SMOTEENN.png](https://raw.githubusercontent.com/LaurenDebes/Credit_Risk_Analysis/main/SMOTEENN.png)
  - <b>Balanced Accuracy Score:</b> 58% predicted correctly, the lowest accuracy score of our models
  - <b>Precision Score:</b> Only 1% in precision, indicating a low likelihood of accuracy and a high number of false positives (low risk classifications). This is the lowest accuracy score of our models.
  - <b>Recall Score:</b> Sensitivity score of 83% for high risk loans
  - <b>Summary:</b> This model may not be the best because the precision/recall are not good enough to state that the model will be good at predicting risk. There is a low f1 score.

## Results -- Ensemble Classifiers

### BalancedRandomForestClassifier Results:
  - ![balancedrandomforestclassifier.png](https://raw.githubusercontent.com/LaurenDebes/Credit_Risk_Analysis/main/balancedrandomforestclassifier.png)
  - <b>Balanced Accuracy Score:</b> 80% predicted correctly
  - <b>Precision Score:</b> Only 3% of the high risk loans were found, this is a very low score. There is likely a high number of false positives.
  - <b>Recall Score:</b> Sensitivity score of 70% for high risk loans
  - <b>Summary:</b>This model may not be the best because the precision/recall are not good enough to state that the model will be good at predicting risk. There is a low f1 score.
  
### EasyEnsembleClassifier Results:
  - ![easyensembleclassifier.png](https://raw.githubusercontent.com/LaurenDebes/Credit_Risk_Analysis/main/easyensembleclassifier.png)
  - <b>Balanced Accuracy Score:</b> 93% predicted correctly
  - <b>Precision Score:</b> 7% of high risk loans were found, this is the highest score of any of our models.
  - <b>Recall Score:</b> Sensitivity score of 91% for high risk loans
  

## Summary
There does not appear to be any positivity bias for reviews in the Vine program. There were actually 4% less 5 star reviews from users of the vine program. An additional analysis that could be done would be to look at the individual customer_ids and see if there are users that always rate things 5 star and to filter them out if so. You could also filter for verified versus unverified purchase to see if that changes the number of 5 star reviews.


