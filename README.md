# Credit Risk Analysis
## Overview
LendingClub, a peer-to-peer lending services company wants to use machine learning to predict credit card risk. Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Lenders use machine learning to analyse risks to know whether or not to approve loan aplications. This provides a quicker and more reliable loan experience. Also, machine learning leads to more accurate identification of good candidates for loans which leads to low default rates.   
In this project, using the credit card dataset from LendingClub, I will employ 6 different techniques to train and evaluate models with unbalanced classes. I will oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample it using the ClusterCentroids algorithm. Then, I will use a combinatorial approach of oversampling and undersampling using the SMOTEENN algorithm.  Afterwards, I will compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. 

After designing and implementing these algorithms I will evaluate their performance and see how well my models predict data.
 

## Results
After the data had been cleaned, our target which is the loan status had the following distribution.

![image0](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/target%20values.png)

This represents 99.5% low risk and just 0.5% high risk.

In examining the resuts of the 6 machine learning models, we will focus on the balanced accuracy scores, the precision and recall scores.  

as well as the Imbalanced Classification Report (ICR) from each model. Of particular interest in the ICR are two figures from the "f1" (F-score) column - the number from the bottom "avg / total" row, as well as the f-score from the "high risk" row, since we're primarily interested in our ability to detect high credit risk individuals.

Using the naive random oversampling algorithm, the balanced accuracy score was 0.65. From the imbalanced classification report, the precision for the high risk was very small with a value of 0.01 while the recall was 0.68. The precision for the low risk was 1 with a recall of 0.62. The f1 for high risk was 0.02 and that of low risk was 0.76.

![image1](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/naive%20oversampling%20accuracy.png)

![image2](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/naive%20oversampling%20report.png)


Using the SMOTE oversampling algorithm, the balanced accuracy score was 0.66. From the imbalanced classification report, the precision for the high risk was very small with a value of  0.01 while the recall was 0.63. The precision for the low risk was 1.00 with a recall of 0.68. The f1 for high risk was 0.02 and that of low risk was 0.81.

![image3](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/SMOTE%20oversampling%20accuracy.png)

![image4](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/SMOTE%20oversampling%20report.png)

Using the Cluster Centroids algorithm for undersampling, the balanced accuracy score was 0.54. From the imbalanced classification report, the precision for the high risk was very small with a value of  0.01 while the recall was 0.69. The precision for the low risk was 1.00 with a recall of 0.4. The f1 for high risk was 0.01 and that of low risk was 0.57.

![image5](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/undersampling%20accuracy.png)

![image6](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/undersampling%20report.png)

Using a combination of over-sampling and under-sampling (SMOTEENN algorithm),  the balanced accuracy score was 0.68. From the imbalanced classification report, the precision for the high risk was very small with a value of  0.01 while the recall was 0.76. The precision for the low risk was 1.00 with a recall of 0.59. The f1 for high risk was 0.02 and that of low risk was 0.74.

![image7](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/SMOTEENN%20Accuracy.png)

![image8](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/SMOTEENN%20report.png)

Using the balanced random forest classifier ensemble algorithm, the balanced accuracy score was 0.79. From the imbalanced classification report the precision for the high risk was very small with a value of 0.03 while the recall was 0.70. The precision for the low risk was 1.00 with a recall of 0.87. The f1 for high risk was 0.06 and that of low risk was 0.93.

![image9](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/ensemble%20accuracy.png)

![image10](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/ensemble%20report.png)

Using the Easy Ensemble AdaBoost classifier algorithm,  the balanced accuracy score was 0.93. From the imbalanced classification report, the precision for the high risk was very small with a value of  0.09 while the recall was 0.92. The precision for the low risk was 1.00 with a recall of 0.94. The f1 for high risk was 0.16 and that of low risk was 0.97.

![image11](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/AdaBoost%20Accuracy.png)

![image12](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/AdaBoost%20Report.png)

Preision measures what percentage of the predicted values are correct. For this analysis the precision for the high risk was always too low. The highest precision we could get was 0.16b using the AdaBoost model. This value is not good enough 
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

In summary, I will recommend the Easy Ensemble AdaBoost classifier algorithm as the best option for detecting whether a client is a high risk or low risk for loan application. This is because it had the highest accuracy of 0.552. Its precion and recall for high risk was and respectively. While its precision and recsall for lowrisk was and respectively. So we can conclude that this model is good enough at predicting credit risk. 



We coulfd have created a standard scaler instance to improve upon our results . 



In the first four models we undersampled, oversampled and did a combination of both to try and determine which model is best at predicting  We compared two ensemble algorithms



In our first four models our accuracy score is not as high as the ensemble classifiers and the recall in the oversampling/undersampling/mixed models is low as well. Typically in your models you want a good balance of recall and precision which is why I recommend the ensemble classifiers over the first four models. It appears that the Easy Ensemble had the best balance of all the models because of it's high accuracy score and good balance of precision and recall scores.
