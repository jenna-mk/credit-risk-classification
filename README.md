# Module 20 Challenge: Credit Risk Classification Using Logistical Regression
The purpose of this analysis is to take a dataset of historical lending activity from a peer-to-peer lending services company and use it to build a model that can identify the creditworthiness of borrowers. The dataset included information such as loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks, total debt, and loan status. The column I need to predict is loan status, which will enable me to use the model to judge whether a borrower is healthy or high-risk based on the other listed factors.

In this analysis, I created labels and features, split the data into training and testing sets, created a logistic regression model with the split data, fit the model, and generated predictions based on this model. 

Since the dataset is imbalanced, with more than 30x the instances of healthy loans versus high-risk loans, I created two machine learning models. The first is fit to the original data, and the second is fit to resampled data, where randomly selected data from the minority class (in this case, the high-risk loans) is duplicated until the instances of healthy versus high-risk loans are equal to one another. 

## Results
The results for the models are as follows:

* Machine Learning Model 1 (Original Data):
  * This logistic regression model predicts the labels very well, with a balanced accuracy score of 94.4%. The classification report shows that, for healthy loans (labelled 0), the model is able to make predictions with precision of 1.00 and recall of 1.00. For high-risk loans (labelled 1), the model is able to make predictions with precision of 0.87 and recall of 0.94.

* Machine Learning Model 2 (Resampled Data):
  * This logistic regression model predicts the labels incredibly well, with a balanced accuracy score of 99.6%. The classification report shows that, for healthy loans, the model is able to make predictions with precision of 1.00 and recall of 1.00. For high-risk loans, this model is able to make predictions with precision of 0.87 and recall of 1.00.

## Summary
Both models perform very well, but the model fit to the resampled data does perform better, as the recall score is higher (which means the model is better able to correctly identify instances of high-risk loans). Additionally, this model includes more balanced data. As with most problems, which model to use depends on what we want to use it for. In this case, we would want to make sure that we are not giving loans to borrowers who are likely to default. Although the precision score for the model fit to the resampled data indicates that there are still borrowers being classified as high-risk when they are not, the recall score of 1.00 ensures all high-risk borrowers are correctly identified. Thus, for our purposes, the model fit with the resampled data is the better choice.
