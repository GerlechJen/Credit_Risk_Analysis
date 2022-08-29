# Credit Risk Analysis
## Overview
LendingClub, a peer-to-peer lending services company wants to use machine learning to predict credit card risk. Lenders use machine learning to analyse risks to know whether or not to approve loan aplicatoions. This will provide a quicker and more reliable loan experience. Also, machine learning will lead to a more accurate identification of good candidates for loans which will lead to low default rates. Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans.  
In this role, using the credit card credit dataset from LendingClub, I will employ different techniques to train and evaluate models with unbalanced classes. I will oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample it using the ClusterCentroids algorithm. Then, I will use a combinatorial approach of oversampling and undersampling using the SMOTEENN algorithm.  Afterwards, I will compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. 

After designing and implementing these algorithms I will evaluate their performance and see how well my models predict data.






 using Python and scikit-learn library 
imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

 



## Results
The results show that:

Out of 84 good loan applications (Actual 0), 50 were predicted to be good (Predicted 0), which we call true positives.
Out of 84 good loan applications (Actual 0), 34 were predicted to be bad (Predicted 1), which are considered false negatives.
Out of 41 bad loan applications (Actual 1), 22 were predicted to be good (Predicted 0) and are considered false positives.
Out of 41 bad loan applications (Actual 1), 19 were predicted to be bad (Predicted 1) and are considered true negatives.



## Summary

you’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.
