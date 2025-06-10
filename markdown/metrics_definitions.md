# Evaluation and Optimization Metrics

Metric is a functional value that describes model quality.

When training a model, it is optimized internally using a metric cross-entropy for Classification and RMSE for Regression, which ensures the model learns effectively. However, the evaluation metric a user selects is used to determine which model version performs best for users specific needs.

## How it works
1. Cross-Entropy/RMSE Optimization: The model is trained and optimized using cross-entropy/RMSE at every step.
2. Evaluation Metric Selection: User chooses an evaluation metric (e.g., accuracy, F1-score) to assess performance based on their specific goals.
3. Best Model Selection:
   3.1 On the main page, the model metric shown is the one that performed best according to cross-entropy.
   3.2 On the Results tab, the model versions are sorted using user's chosen evaluation metric, and the best version based on this metric is highlighted.

## Evaluation Metrics

### MAE
Mean Absolute Error is the difference between all the observed and predicted values. The direction of the error (positive or negative) does not matter, because the size of the error is calculated by module. Use this metric to minimize the average error.

### MSE
a measure of the quality of an estimator, it is always non-negative, and values closer to zero are better. MSE measures the average of the squares of the errors - that is, the average squared difference between the estimated values and true values. The squaring is necessary to remove any negative signs, it also gives more weight to larger differences, so bigger errors are penalized higher.

### Accuracy
Accuracy represents how accurately a class is predicted. If 73 from 100 predicted records are assigned a correct class, then the accuracy is 0.73 or 73%. The higher the value – the better. Accuracy does not take class imbalance into account. It is best applicable when classes are represented by an approximately equal quantity of samples.

### AUC (ROC AUC)
A Receiver Operating Characteristic Curve is a graphical plot that illustrates the diagnostic ability of a binary classifier system as its discrimination threshold is varied. A classification metric “Area Under the Curve” (AUC) related to the ROC curve represents how effectively the model answers the question “Does the current object belong to the corresponding class?”. The value is always between 0 and 1: The higher = the better; ~0,5 = the worst (the model provides values like random)

### Balanced Accuracy
Balanced Accuracy accounts for imbalanced classes where (for example) one class may be represented by 10% of samples and the second class may be represented by the remaining 90% of samples.

### R2 (Coefficient of Determination)
Coefficient of Determination is the proportion of variance in the dependent variable that is predictable from the independent variables. This metric scores the model with 1 if our model is perfect, and with 0 otherwise. If the Coefficient of Determination is 0.95, then 95% of the data is explained by observed statistics and the trained model.

### Confusion Matrix
Also known as an error matrix, is a specific table layout that helps to visualize the performance of an algorithm. Each row of the Matrix represents the samples in a predicted class while each column represents the samples in an actual class (or vice versa). The Matrix makes it easy to see if the system is confusing two classes. You can find it in the Results tab in each solution with a classification problem.

### F1 Score
Can be interpreted as a weighted average of the precision and recall for each class, where an F1 Score reaches its best value at 1 and worst score at 0. You should use this metric when you want to have a good balance between Precision and Recall.

### Gini
The Gini coefficient applies to binary classification and requires a classifier that can in some way rank examples according to the likelihood of being in a positive class. A Gini value of 0% means that the characteristic cannot distinguish between classes. The Gini coefficient makes sense for the whole collection of predictions and not individual data points. The Gini coefficient only tells if perfect segregation (based on probability predictions) is possible or not and nothing about the probability threshold. In short, there is no relation between probability threshold and Gini. The Gini coefficient provides an accurate model predictive power measure for imbalanced class problems.

### LogLoss
Logarithmic Loss is a measure of prediction confidence level. LogLoss represents the difference between the actual class and the probability of a prediction being in that class. For example, the model correctly predicts a 0.90 probability of being in class 1- that means it is pretty confident, but still, there is 0.1 uncertainty of this prediction; LogLoss penalizes for this uncertainty. The lower the LogLoss score, the better the model\`s predictive power. LogLoss takes into account not the rounded-off predicted class but the probability of the prediction corresponding to a certain class.

### Macro Average Precision
Precision is the fraction of relevant samples among the retrieved samples. The precision score reaches its best value at 1 and the worst score at 0. Precision is intuitively the ability of the classifier not to label as positive a sample that is negative. Use this metric when it is most important to find only relevant samples without mistake even if you may skip some of the relevant samples. Macro Average Precision does not take class imbalance into account. It is best applicable when (for example) three classes of a multiclass classification problem are represented by an approximately equal quantity of samples.

### Macro Average Recall
The Recall is the fraction of relevant samples that have been retrieved over the total amount of relevant samples. The recall score reaches its best value at 1 and worst score at 0. The Recall is intuitively the ability of the classifier to find all the positive samples. Use this metric when it is the most important to find as many relevant samples as possible even if you may also mark some of the wrong examples as relevant. Macro Average Recall does not take class imbalance into account. It is best applicable when (for example) three classes of a multiclass classification problem, represented by an approximately equal quantity of samples.

### Macro Average F1 Score
The F1 score can be interpreted as an arithmetic average of the precision and recall for each class, where an F1 score reaches its best value at 1 and worst score at 0. You should use this metric when you want to have a good balance between Precision and Recall. Macro Average F1 score does not take class imbalance into account. It is best applicable when (for example) three classes of a multiclass classification problem, represented by an approximately equal quantity of samples.

### Precision
Precision is the fraction of relevant samples among the retrieved samples. The precision score reaches its best value at 1 and worst score at 0. Precision is intuitively the ability of the classifier not to label as positive a sample that is negative. Use this metric when the priority is to find only relevant samples without a mistake, even if you may end up skipping some of the relevant samples.

### Recall
Recall is the fraction of relevant samples that have been retrieved over the total amount of relevant samples. The recall score reaches its best value at 1 and worst score at 0. The recall is the ability of the classifier to find all the positive samples. Use this metric when the priority is to find as many relevant samples as possible even if you may also mark some of the wrong examples as relevant.

### RMSE
Root Mean Squared Error represents an error between observed and predicted values (square root of squared average error over all observations). The lower RMSE - the better predictive power the model has. RMSE is always non-negative, and a value of 0 would indicate a perfect fit for the data. It should be used when you want to make a model which would not have big individual errors for every prediction.

### RMSLE
Root Mean Squared Logarithmic Error can be used when one doesn’t want to penalize huge differences when both the values are huge numbers. The lower RMSLE - the better predictive power the model has. RMSLE can also be used when one wants to penalize underestimates more than overestimates.

### RMSPE
Root Mean Squared Percentage Error represents a percentage error between the observed and predicted values measured as the square root of the mean of the squared (difference between the actual values and the predicted values divided by the actual values). The lower the RMSPE – the better the model’s predictive power. RMSPE is always non-negative, and a value of 0 (almost never achieved in practice) would indicate a perfect fit to the data. In general, a lower RMSE is better than a higher one. However, comparisons across different types of data would be invalid because the measure is dependent on the scale of the numbers used. Rows with 0 values in the target variable are filtered out and are not used in the validation pipeline as division by 0 is not possible.

### Weighted Average Precision
Weighted Average Precision accounts for imbalanced classes where (for example) one class may be represented by 10% of samples, the second class may be represented by 60% of samples and the other N classes are represented by the remaining 30% of samples.

### Weighted Average Recall
Weighted Average Recall accounts for imbalanced classes where (for example) one class may be represented by 10% of samples, the second class may be represented by 60% of samples and the other N classes are represented by the remaining 30% of samples.

### Weighted Average F1 Score
Weighted Average F1 Score accounts for imbalanced classes where (for example) one class may be represented by 10% of samples, the second class may be represented by 60% of samples and the other N classes are represented by the remaining 30% of samples.

### The Model Quality Diagram
This plot simplifies the process of evaluating the model quality. The values of all metrics are evaluated on a scale from 0 to 1, where 1 is the most accurate model. It also allows users to understand metric balance for the selected model. When the figure displayed is close to the shape of a regular polygon, that conveys a perfect balance between all metric indicator values.