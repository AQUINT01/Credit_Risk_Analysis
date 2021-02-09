# Credit Risk Analysis
## Overview :

Credit Risk is an inherently imbalanced classification problem. In the following analysis, I explored how various Machine Learning algorithm techniques can be used to train and evaluate models with imbalanced classes  and compare their performance to a real-world setting from LendingClub, a peer2peer lending services company.


## Results: 

### Evaluation Metrics
With regards to the evaluation of the models, it’s worth mentioning that I considered the Precision, Recall and Balanced Accuracy scores as evaluation metrics for the following reasons:


>    **Precision** provides the proportion of positive identifications that are truly correct.
>    **Recall** determines the proportion of real positives that are correctly identified.
>    **Balanced Accuracy** accounts for both the positive and negative outcome classes and doesn't mislead with imbalanced data.

- ### Random Oversampling
<img width="1293" src="https://github.com/AQUINT01/Credit_Risk_Analysis/blob/main/images/oversampling.png">

The precision ("pre" column) is very low for the high-risk class, (*1%*) and very high for the low-risk class (*100%*), while the recall ("rec" column) is in line for both classes.
The balanced accuracy scored at 67.42%.

- ### SMOTE Oversampling
<img width="1293" src="https://github.com/AQUINT01/Credit_Risk_Analysis/blob/main/images/SMOTE.png">

This method, like random oversampling, produced similar precision, *1%* for high-risk and *100%* for low-risk classes while the recall value decrease to *63%* for the high-risk class and increased for the low-risk class. The balanced accuracy score decreased as well from the previous random oversampling, *66.23%*.

- ### Undersampling
<img width="1293" src="https://github.com/AQUINT01/Credit_Risk_Analysis/blob/main/images/Undersampling.png">

The precision scored opposite results for both classes as previously reported but the recall slightly increased to 67% for the high-risk class and decreased to 42% for the low-risk class. 
The balance accuracy rate remain the same at *66.23%*.

- ### Combination ( Over- and Under-sampling )
<img width="1293"
src="https://github.com/AQUINT01/Credit_Risk_Analysis/blob/main/images/CombineSampling.png">

The balanced accuracy score decreased to *54.7%* from 66.23%, while the recall for both classes increased, *72%* and *57%* respectively.  The precision remain unchanged for both from previous models.

- ### Balanced Random Forest Classifier
<img width="1293" src="https://github.com/AQUINT01/Credit_Risk_Analysis/blob/main/images/BalRandomForest.png">

This method yield a balance accuracy score of  *78.92%*.  The precision rate remain mostly the same with previous model results with a slight increase to the high-risk class of *4%*. The recall rate was higher for the low-risk class, *89%*, versus the high-risk class, *69%*. 

- ### Easy Ensemble AdaBoost Classifier
<img width="1293" src="https://github.com/AQUINT01/Credit_Risk_Analysis/blob/main/images/EasyEnsembleAdaboost.png">

The recall scores were in line for both classes, *89%* and *94%* but the precision rates continued to show significant differences, high-risk at *9%* and low-risk at *100%*.  Out of all the models, the balance accuracy scored the highest at  *91.8%* for this method.

## Summary: 

The main objective of this exercise was to build machine learning algorithms that would be able to identify potential defaulters and therefore reduce company loss. The best model possible would be the one that could minimize false negatives, identifying all defaulters among the client base, while also minimizing false positives, preventing clients to be wrongly classified as defaulters.

Meeting these requirements can be quite tricky as there is a tradeoff between precision and recall, meaning that increasing the value of one of these metrics often decreases the value of the other. Considering the importance of minimizing company loss, I decided to give more emphasis on reducing false positives, searching for the best hyperparameters that could increase the recall rate. 

As a result, I recommend using the **Easy Ensemble Adaboost** model with a recall of **89%**  for the high-risk class and the highest balanced accuracy score of **92%**. 
