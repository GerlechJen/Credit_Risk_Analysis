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

 F1 score where the best score is 1.0 and the worst is 0.0.
 



## Summary

When it comes to lending, if we approve a loan for a high risk client it will be a loss to LendingClub. Same way if we reject loans to people who are worth it, we would be losing valuable clients to competitors. In this case, we would want to find a good balance between precision and sensitivity (recall).  Accuracy can help here as it accounts for both recall and precision. However, f1 score plays a more important role as it is the weighted average of the recall and precision.

Amongst all the 6 models, the **Easy Ensemble AdaBoost Classifier** algorithm gave the best results. This model had the best balance of all the models because of it's higher accuracy score and relatively higher f1 score.

Precision is a measure of how reliable a positive classification is. It measures what percentage of the predicted values are correct. For this analysis, the precision for the high risk was always very low. It means the errors in predicting high risks is very high. The highest precision obtained was 0.09 using the AdaBoost model. This precision is not good enough for bad loan applications as it implies that amongst the people predicted to be high risk, just 9% of them are actually high risk clients. This is not good for business as it means that a lot of good clients will be turned away.


The recall of 0.92 means that 92% of high risks were predicted which is very good considering just 8% could not be predicted  However, as explained earlier accuracy score and f1 score are the best options for detecting the efficiency of our model. Although the accuracy score was very high at **0.93** the f1 score for high risk prediction was very low at just **0.16** which implies that there is no balance between the recall and precision of the high risk

In summary, I will not recommend using any of these algorithms, as they were all unable to efficiently predict high risk and low risk clients. 

----

**Completed by:** Jennifer Anno-Kusi

**Email:** jannokusi@gmail.com 
