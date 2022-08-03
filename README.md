# Credit Risk Analysis
Module 17 Challenge
## Overview of Analysis
We have been asked to use supervised machine learning to analyze credit card risk to classify loans as either high risk or low risk. We will be using a dataset from LendingClub to oversample and undersample the data (and use a combination approach), to get a better picture of the credit risk to make predictions. We'll compare the results from two learning models to predict the risk. 

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
  ![balancedrandomforestclassifier.png](https://raw.githubusercontent.com/LaurenDebes/Credit_Risk_Analysis/main/balancedrandomforestclassifier.png)
  - <b>Balanced Accuracy Score:</b> 80% predicted correctly
  - <b>Precision Score:</b> Only 3% of the high risk loans were found, this is a very low score. There is likely a high number of false positives.
  - <b>Recall Score:</b> Sensitivity score of 70% for high risk loans
  - <b>Summary:</b> This model may not be the best because the precision/recall are not good enough to state that the model will be good at predicting risk. There is a low f1 score.
  
### EasyEnsembleClassifier Results:
  ![easyensembleclassifier.png](https://raw.githubusercontent.com/LaurenDebes/Credit_Risk_Analysis/main/easyensembleclassifier.png)
  - <b>Balanced Accuracy Score:</b> 93% predicted correctly
  - <b>Precision Score:</b> 7% of high risk loans were found, this is the highest score of any of our models.
  - <b>Recall Score:</b> Sensitivity score of 91% for high risk loans
  - <b>Summary:</b> This is our best model, sensitivity is more important for the type of data we are analyzing, but this is an extremely low precision score still.

## Summary
In general, each of these models did not perform to a high enough level for recommendation to use. Each of the models had a very low precision, indicating a high number of false positives. The recall (sensitivity) scores were the best for the RandomEnsembleClassifier (93%) and SMOTEENN (83%). Overall the EasyEnsembleClassifier did the best, but with only a 7% precision score I would not be confident in recommending the model. However, in our situation, a high sensitivity is more important, it would lead to fewer false negatives which would lead to less risk and help to make wise financial decisions. The harmonic mean (f1 score) is low for each of the models, due to the imbalance between the sensitivity and precision scores.
