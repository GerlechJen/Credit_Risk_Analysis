# Credit Risk Analysis
## Overview
LendingClub, a peer-to-peer lending services company wants to use machine learning to predict credit card risk. Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Lenders use machine learning to analyse risks to know whether or not to approve loan aplications. This provides a quicker and more reliable loan experience. Also, machine learning leads to more accurate identification of good candidates for loans which leads to low default rates.   
In this project, using the credit card dataset from LendingClub, I will employ different techniques to train and evaluate models with unbalanced classes. I will oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample it using the ClusterCentroids algorithm. Then, I will use a combinatorial approach of oversampling and undersampling using the SMOTEENN algorithm.  Afterwards, I will compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. 

After designing and implementing these algorithms I will evaluate their performance and see how well my models predict data.






 using Python and scikit-learn library 
imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

 

## Results
Precision is the measure of how reliable a positive classification is. From our results, the precision for the good loan applications The precision for the bad loan applications 

Recall is the ability of the classifier to find all the positive samples. A low recall is indicative of a large number of false negatives.

 F1 score is a weighted average of the true positive rate (recall) and precision, where the best score is 1.0 and the worst is 0.0.
 
 Support is the number of actual occurrences of the class in the specified dataset. For our results, there are 84 actual occurrences for the good loans and 41 actual occurrences for bad loans.




The results show that:

Out of 84 good loan applications (Actual 0), 50 were predicted to be good (Predicted 0), which we call true positives.
Out of 84 good loan applications (Actual 0), 34 were predicted to be bad (Predicted 1), which are considered false negatives.
Out of 41 bad loan applications (Actual 1), 22 were predicted to be good (Predicted 0) and are considered false positives.
Out of 41 bad loan applications (Actual 1), 19 were predicted to be bad (Predicted 1) and are considered true negatives.



## Summary

In summary, this model may not be the best one for preventing fraudulent loan applications because the model's accuracy, 0.552, is low, and the precision and recall are not good enough to state that the model will be good at classifying fraudulent loan applications. Modeling is an iterative process: you may need more data, more cleaning, another model parameter, or a different model. It's also important to have a goal that's been agreed upon, so that you know when the model is good enough.

you’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.


We coulfd have created a standard scaler instance to improve upon our results . 
