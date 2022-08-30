# Credit Risk Analysis
## Overview
LendingClub, a peer-to-peer lending services company wants to use machine learning to predict credit card risk. Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Lenders use machine learning to analyse risks to know whether or not to approve loan aplications. This provides a quicker and more reliable loan experience. Also, machine learning leads to more accurate identification of good candidates for loans which leads to low default rates.   
In this project, using the credit card dataset from LendingClub, I will employ 6 different techniques to train and evaluate models with unbalanced classes. I will oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample it using the ClusterCentroids algorithm. Then, I will use a combinatorial approach of oversampling and undersampling using the SMOTEENN algorithm.  Afterwards, I will compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. After designing and implementing these algorithms, I will evaluate their performance and see how well my models predict data.
 

## Results
After the loan data had been transformed and cleaned, our target, which is the loan status had the following distribution.

![image0](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/target%20values.png)

This represents 99.5% low risk and just 0.5% high risk clients. Our primary goal here is to get a model that can efficiently detect high credit risk clients. 

In examining the resuts of the 6 machine learning models, we will focus on the balanced accuracy scores, precision, recall and f1 scores.  

Using the **Naive Random Oversampling** algorithm, the balanced accuracy score was **0.65**. From the imbalanced classification report, the precision for the high risk was very small with a value of **0.01** while the recall was **0.68**. The precision for the low risk was **1.00** with a recall of **0.62**. The f1 for high risk was **0.02** and that of low risk was **0.76**. This low f1 value for the high risk implies that there is a pronounced imbalance between recall and precision for high risk. 

![image1](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/naive%20oversampling%20accuracy.png)

![image2](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/naive%20oversampling%20report.png)


Using the **SMOTE Oversampling** algorithm, the balanced accuracy score was slightly higher at **0.66**. From the imbalanced classification report, the precision for the high risk was also very small with a value of  **0.01** while the recall was **0.63**. The precision for the low risk was **1.00** with a recall of **0.68**. The f1 for high risk was **0.02** and that of low risk was **0.81**. The low f1 value means that there is no balance between the recall and precision of the high risk. 

![image3](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/SMOTE%20oversampling%20accuracy.png)

![image4](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/SMOTE%20oversampling%20report.png)

Using the **Cluster Centroids** algorithm for undersampling, the balanced accuracy score was **0.54**  which is lower than those obtained for the two oversampling methods. From the imbalanced classification report, the precision for the high risk was very small with a value of  **0.01** while the recall was **0.69**. The precision for the low risk was **1.00** with a recall of **0.40**. The f1 for high risk was **0.01** and that of low risk was **0.57**.

![image5](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/undersampling%20accuracy.png)

![image6](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/undersampling%20report.png)

Using a combination of over-sampling and under-sampling **(SMOTEENN algorithm)**,  the balanced accuracy score was **0.68**. From the imbalanced classification report, the precision for the high risk was **0.01** while the recall was **0.76** which is the highest recall so far recorded from these 4 models. The precision for the low risk was **1.00** with a recall of **0.59**. The f1 for high risk was **0.02** and that of low risk was **0.74**.

![image7](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/SMOTEENN%20Accuracy.png)

![image8](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/SMOTEENN%20report.png)

Using the **Balanced random forest Classifier Ensemble** algorithm, the balanced accuracy score was **0.79**. From the imbalanced classification report, the precision for the high risk increased slightly to **0.03** while the recall was **0.70**. The precision for the low risk was once again **1.00** with a recall of **0.87**. The f1 for high risk was **0.06** and that of low risk was **0.93**.

![image9](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/ensemble%20accuracy.png)

![image10](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/ensemble%20report.png)

Using the **Easy Ensemble AdaBoost Classifier** algorithm,  the balanced accuracy score was **0.93**. From the imbalanced classification report, the precision for the high risk had the highest ever recorded value **0.09** while the recall was also very high at **0.92**. The precision for the low risk was maintained at **1.00** with an equally high recall of **0.94**. The f1 for high risk saw a higher value of **0.16** and that of low risk was also very high at **0.97**.

![image11](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/AdaBoost%20Accuracy.png)

![image12](https://github.com/GerlechJen/Credit_Risk_Analysis/blob/main/Images/AdaBoost%20Report.png)


Recall is the ability of the model to find all the positive samples. A low recall is indicative of a large number of false negatives.

 F1 score is a weighted average of the true positive rate (recall) and precision, where the best score is 1.0 and the worst is 0.0.
 



## Summary

In summary, I will recommend the Easy Ensemble AdaBoost classifier algorithm as the best option for detecting whether a client is a high risk or low risk for loan application. This is because it had the highest accuracy of 0.552. Its precion and recall for high risk was and respectively. While its precision and recsall for lowrisk was and respectively. So we can conclude that this model is good enough at predicting credit risk. 

Preision measures what percentage of the predicted values are correct. For this analysis the precision for the high risk was always too low. The highest precision we could get was 0.16b using the AdaBoost model. This value is not good enough 
Precision is the measure of how reliable a positive classification is. From our results, the precision for the good loan applications The precision for the bad loan applications 

In this analysis high accuracy is not our prioritize measure. . We want our selected model to be able to detect well clients who have a high risk status.In all th emodels the models the precison was veryy low  A  high number of people who were low risk were also predicted to be high risk . 

It means the errors in predicting high risks is very high. This is not good as it means that good clients will be turned away. 


The recall of 92% means the percentage of high risks that were detected was very high at 0.92 which means that the model predicts high risk clients well.  


We coulfd have created a standard scaler instance to improve upon our results . 



In the first four models we undersampled, oversampled and did a combination of both to try and determine which model is best at predicting  We compared two ensemble algorithms



In our first four models our accuracy score is not as high as the ensemble classifiers and the recall in the oversampling/undersampling/mixed models is low as well. Typically in your models you want a good balance of recall and precision which is why I recommend the ensemble classifiers over the first four models. It appears that the Easy Ensemble had the best balance of all the models because of it's high accuracy score and good balance of precision and recall scores.



Even when it's balanced accuracy and average F-score were above 90%, it's F-score for high-risk prediction was no better than 0.16. In the end, I would advise against using any of these algorithms, as it would put creditors as too great of risk being unable to accurately predict who the high-risk clients/debtors would be.


----

**Completed by:** Jennifer Anno-Kusi

**Email:** jannokusi@gmail.com 

