# Credit-Risk-Analysis-ML
Supervised machine learning to determine credit worthiness

## Analysis Overview
This analysis utilized various machine learning methods to predict credit risk. 

## Results

RandomOverSampler model

Balanced Accuracy Score: .64

Confusion Matrix: 

[[   54    33]

 [ 5945 11173]]

![Naive Oversampling](https://github.com/tbrech4/Credit-Risk-Analysis-ML/blob/main/Resources/test1classification.png)

The F1 score is very low - .02, because of the low precision in predicting high_risk cases. This model should not be used

SMOTE Oversampling model

Balanced Accuracy Score: .63

Confusion Matrix: 

[[   54    33]

 [ 6165 10953]]

![SMOTE](https://github.com/tbrech4/Credit-Risk-Analysis-ML/blob/main/Resources/test2classification.png)

Again, this model should not be used because of the low F1 score (.02)driven by the low precision in predicting high-risk cases. 


Cluster Centroids model

Balanced Accuracy Score: .51

Confusion Matrix: 

[[   51    36]

 [ 9683 7435]]

![Cluster Centroids](https://github.com/tbrech4/Credit-Risk-Analysis-ML/blob/main/Resources/test3classification.png)

This model is even worse than the previous two according to its F1 score of .01 - again driven by a low precision in predicting high_risk. A model should not be used if it is unable to predict what you are looking for.

SMOTEENN model

Balanced Accuracy Score: .62

Confusion Matrix: 

[[   62    25]

 [ 7926 9192]]

![SMOTEENN](https://github.com/tbrech4/Credit-Risk-Analysis-ML/blob/main/Resources/test4classification.png)

This model is similar to the first two in terms of the F1 score being too low to use for reliable prediction making. The low sensitivity is driven by its low precision in high_risk. This would make sense, as this was the same situation for the other models. So far, none of the models have shown much value for this dataset.


BalancedRandomForestClassifier model

Balanced Accuracy Score: .79

Confusion Matrix: 

[[   58    29]

 [ 1560 15558]]

![BRFC](https://github.com/tbrech4/Credit-Risk-Analysis-ML/blob/main/Resources/test5classification.png)

This model's balanced accuracy score is better than prior models, but the low precision in predicting high_risk candidates causes the F1 score to be fairly low at .07. 


Easy Ensemble AdaBoost model

Balanced Accuracy Score: .79

Confusion Matrix: 

[[   79    8]

 [ 979 16139]]

![AdaBoost](https://github.com/tbrech4/Credit-Risk-Analysis-ML/blob/main/Resources/test6classification.png)

AdaBoost is the most promising model due to its highest high_risk precision & F1 value of .14. However, a precision of 7% is still concerning. 


## Summary

All of the models used in this analysis suffer from low precision in predicting high_risk candidates. The ensemble methods were more accurate than the sampling models. 

The recall value of the EasyEnsembleClassifier model is 91% - this would be helpful in detecting high risk cases. However, you have a lot of low_risk cases that would falsely be labeled high_risk. 

I would recommend having someone check all high_risk labeled cases to make sure they don't get incorrectly labeled. This should still be less time required to manually process all applications. 