# credit-risk-classification
Module 20 Challenge

## Overview of the Analysis

The purpose of this analysis was to develop a predictive model to classify potential lending customers as either "healthy" which means good candidates for loans, or "risky" which means they have a high risk of defaulting on the loan. The features of this dataset were pieces of financial information that are correlated with the chance of success or failure of a loan. These features included, but were not limited to: loan size, interest rate, income, and total debt. These features, along with the rest, provided information about the potential customer's financial health and thus helped us decide whether they were good candidates for a future loan. 

For this analysis, I used the Logistic Regression model. This model uses the sigmoid function where each independent variable is associated with a coefficient that quantifies its impact on the odds of the outcome. Therefore, higher coefficients reflect a variable's higher independent influence on the predicted probability of the outcome. As a general summary, this model will take in some training data, build the logistic function that best predicts the training data, and then use other data that it was not trained on, in order to make predictions about the classification of the loan applications. 

This specific dataset had about 30x more data points that were considered "healthy" than ones considered "risky". This discrepancy in values skewed the model's learning process and led to unfavorable predictions for the class with fewer data points ("risky"). To combat this I used "resampling" to even out the number of data points for each class. In my model's case, we used oversampling, which means duplicating samples from the minority class in order to increase its representation, and thus improve the effectiveness in which the model can predict the minority class. 


## Results

The results analysis was based on the balanced accuracy, precision, and recall scores for the models. The balanced accuracy score is a modification of the regular accuracy score used to account for datasets with uneven output classes. Essentially, the balanced accuracy takes an even weight average of the recalls, rather than a weighted average which the regular accuracy score does. This results in an accuracy score that more heavily weighs the minority class's recall value relative to its actual weighting in the dataset. 

The precision calculation tells us, of the total number of classifications made for a certain class (negative or positive, i.e., healthy or risky), how many were actually correct. In other words, for the positive class, the equation would be [True positives / (True positives + False positives)].

The recall calculation tells us, of the actual positives/negatives, how many were correctly predicted as positive/negative. For the positive class, the equation would be [True positives / (True positives + False negatives)].


* Logistic Regression Model - Original Data:
  * The balanced accuracy was ~97.2%, meaning that the model was very accurate at predicting the outcomes for
  new data.
  * The precision and recall values for the Healthy class were both ~100% meaning that almost all of the negative 
  classifications made were correct, and of the actual negative classifications, the model captured almost all of 
  them.
  * The precision and recall values for the Risky class were ~87% and ~95% respectively. This is a much bigger drop 
  off, especially in precision. This shows that of the risky classifications made by the model, fewer of them were 
  actually risky, thus more false positives. 



* Logistic Regression Model - Resampling Data:
  * The balanced accuracy was ~99.6%, meaning that the model significantly more accurate at correctly predicting the 
  outcomes for new data.
  * The precision and recall values for the Healthy class were both ~100% meaning that almost all of the negative 
  classifications made were correct, and of the actual negative classifications, the model captured almost all of 
  them.
  * The precision and recall values for the Risky class were ~87% and ~100% respectively. This is a much bigger drop 
  off, especially in precision. This shows that of the risky classifications made by the model, fewer of them were 
  actually risky, thus more false positives. But of the applications that were actually risky, this model was able 
  to almost fully capture them (~100% recall) better than the original data (~ 95%)

## Summary

In conclusion, it is clear that in the context of this dataset, the second model (Logistic Regression Model - Resampling Data) would be the preferred method. This model demonstrated a higher overall balanced accuracy score. The precision and recall values for the Healthy class were almost identical for both models, while the Risky class saw a significant improvement in the recall value and maintained the same precision value. The improvements in recall for the minority class while maintaining or improving in all the other measurements make this model the clear recommendation for this dataset. 

