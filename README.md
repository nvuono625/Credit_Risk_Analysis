# Overview 

Before a loan is granted, a credit risk analysis needs to be conducted on the recipient to prevent high default rates. In this analysis, a few supervised machine learning models will be used to determine credit risks. [LoanStats_2019Q1.csv] contains a vast list of loans with categorical information about the recipient to grade the credit risk as either a good or risky loan. Multiple supervised machine learning models will try to predict the credit risk but which model will be the most effective?
_____

# Results

## Naïve Random Oversampling
#### Balanced Accuracy Score
- Balanced Accuracy Score: 64.47%

#### Confusion Matrix
|                | Predicted True | Predicted False |
|:--------------:|:--------------:|:---------------:|
| Actually True  |       71       |       30        |
| Actually False |      7073      |      10031      |

#### Classification Report
![/Resources/Naive_Random_Oversampling.png](/Resources/Naive_Random_Oversampling.png)
- Precision
	- High Risk: 1%
	- Low Risk: 100%
- Recall
	- High Risk: 70%
	- Low Risk: 59%
______

## SMOTE Oversampling
#### Balanced Accuracy Score
- Balanced Accuracy Score: 66.23%

#### Confusion Matrix
|                | Predicted True | Predicted False |
|:--------------:|:--------------:|:---------------:|
| Actually True  |       64       |       37        |
| Actually False |      5286      |      11818      |

#### Classification Report
![/Resources/SMOTE_Oversampling.png](/Resources/SMOTE_Oversampling.png)
- Precision
	- High Risk: 1%
	- Low Risk: 100%
- Recall
	- High Risk: 63%
	- Low Risk: 69%
______

## Cluster Centroids Undersampling
#### Balanced Accuracy Score
- Balanced Accuracy Score: 54.42%

#### Confusion Matrix
|                | Predicted True | Predicted False |
|:--------------:|:--------------:|:---------------:|
| Actually True  |       70       |       31        |
| Actually False |     10341      |      6763       |

#### Classification Report
![/Resources/Cluster_Centroids_Undersampling.png](/Resources/Cluster_Centroids_Undersampling.png)
- Precision
	- High Risk: 1%
	- Low Risk: 100%
- Recall
	- High Risk: 69%
	- Low Risk: 40%
______

## SMOTEENN Combination (Over and Under) Sampling
#### Balanced Accuracy Score
- Balanced Accuracy Score: 63.65%

#### Confusion Matrix
|                | Predicted True | Predicted False |
|:--------------:|:--------------:|:---------------:|
| Actually True  |       70       |       31        |
| Actually False |      7185      |      9919       |

#### Classification Report
![/Resources/SMOTEENN_Combination_(Over_and_Under)_Sampling.png](/Resources/SMOTEENN_Combination_(Over_and_Under)_Sampling.png)
- Precision
	- High Risk: 1%
	- Low Risk: 100%
- Recall
	- High Risk: 69%
	- Low Risk: 58%
______

## Balanced Random Forest Classifier
#### Balanced Accuracy Score
- Balanced Accuracy Score: 78.85%

#### Confusion Matrix
|                | Predicted True | Predicted False |
|:--------------:|:--------------:|:---------------:|
| Actually True  |       71       |       30        |
| Actually False |      2153      |     14951       |

#### Classification Report
![/Resources/Balanced_Random_Forest_Classifier.png](/Resources/Balanced_Random_Forest_Classifier.png)
- Precision
	- High Risk: 3%
	- Low Risk: 100%
- Recall
	- High Risk: 70%
	- Low Risk: 87%
______

## Easy Ensemble ADABoost Classifier
#### Balanced Accuracy Score
- Balanced Accuracy Score: 93.17%

#### Confusion Matrix
|                | Predicted True | Predicted False |
|:--------------:|:--------------:|:---------------:|
| Actually True  |       93       |        8        |
| Actually False |      983       |     16121       |

#### Classification Report
![/Resources/Easy_Ensemble_ADABoost_Classifier.png](/Resources/Easy_Ensemble_ADABoost_Classifier.png)
- Precision
	- High Risk: 9%
	- Low Risk: 100%
- Recall
	- High Risk: 92%
	- Low Risk: 94%
______

# Summary

The confusion matrix can be reviewed to generate the accuracy, precision and sensitivity of each model by following the below information:

|                | Predicted True | Predicted False |
|:--------------:|:--------------:|:---------------:|
| Actually True  | True Positive  |  False Negative |
| Actually False | False Positive |  True Negative  |

- Accuracy:
	- = (True Positive + True Negative) / Total
- Precision:
	- = True Positive / (True Positive + False Positive)
- Sensitivity:
	- = True Positive / (True Positive + False Negative) 

It is necessary for all scores to be stable and impartial. The only model that is and would be recommended is the Easy Ensemble ADABoost Classifier model. It Balanced Accuracy Score is significantly higher than all other models and the precison and recall scores as well significantly higher and stable.
