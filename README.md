# Breast Cancer Classification Problem

Used classification technique on the Breast Cancer dataset. 
**Data:**
https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/wdbc.data

**Description:**
https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/wdbc.names


Specifically, built a decision tree, logistic regression and k-nearest neighbors that predicts the
diagnose result based on ten real-valued features (mean, standard error, and "worst" or largest of
these features). Explored how well different model perform for several different parameter values.
Understood when overfitting and underfitting are observed. Showed how we set the model that provides the best
predictive performance. Present a brief overview of your predictive modeling process, explorations,
and discussed final results.
All the information about the model “goodness” (confusion matrix, predictive accuracy, classification error, precision, recall,
f-measure) are discussed.

**Decision Tree:**

● Overfitting and Underfitting:
We have split the data into 80-20 proportion of training and test. On comparing the accuracy of
the training and test data for max_depth ranging from 1 to 20, we have obtained the above graph.
As can be seen from the plot, the training data underfits the test data max_depth less than equal to
3. Similarly, the training data with max_depth of 13 and greater, the accuracy on test data is poor
which indicates overfitting in our training data.

<img width="334" alt="image" src="https://github.com/p-saraswat/Breast_Cancer_Classification/assets/121529081/9ccbe2b9-7e61-47a1-a175-ae8e678baf43">


*Predictive performance:*
We have used a function called grid search which provides the most optimized combination of
the selected hyperparameters. We created a 2*20 matrix grid with rows having max_depth
ranging from 1 to 20 and the column contains criterion Gini and Entropy. The output of the grid
search gave us max_depth =4 and Criterion = Entropy. The Max_depth was in line with what we
observed previously from the underfitting and overfitting plot. After tuning the hyperparameter
to max_depth = 4 and Criterion = Entropy, we ran the Decision tree algorithm with these
hyperparameters on the test data. We obtained an accuracy of 95.38%.

● Model Goodness:

Based on the result of the grid search we fixed the hyper-parameter of max_depth to 4 and criteria
as ‘entropy’. The model was thus obtained has an accuracy of 95%. Other confusion matrix for
the final model are shown below:

<img width="392" alt="image" src="https://github.com/p-saraswat/Breast_Cancer_Classification/assets/121529081/d0de4128-8fc1-4121-8b03-43d2762478dd">




**Logistic Regression:**

● Overfitting and Underfitting:
The two hyperparameters for logit are C and penalty (‘L1,L2’). We varied C over the range of
0.001 to 100 with a step size of 1 to check the accuracy of testing and training data.
We found that for very low values of ‘C’ (= i.e., <10, the model is underfitting.
For C values in the range of 10-40, both the training and testing accuracies are consistent at
around 97% and 96% respectively. For C values above 40, we see that the model performance is
not very consistent.


<img width="310" alt="image" src="https://github.com/p-saraswat/Breast_Cancer_Classification/assets/121529081/616245e3-06b4-4f5b-8d8e-cb56f27e85d9">


*Predictive performance:*
To find the best ‘C’, we used the ‘GridsearchCV’ function with ‘C’, and the optimal value of
‘C’ = 54 was used for the final model. This gave us a testing accuracy of 95.6% and training
accuracy of 96.4%.

● Model Goodness:

<img width="446" alt="image" src="https://github.com/p-saraswat/Breast_Cancer_Classification/assets/121529081/0c8dce30-664a-44ff-a9c6-f950397aa23b">



K-Nearest Neighbours:

● Overfitting and Underfitting:

<img width="437" alt="image" src="https://github.com/p-saraswat/Breast_Cancer_Classification/assets/121529081/27e5fdc9-b9b0-43b8-be47-7c00dccee332">

Below K = 5, the test accuracy is very poor which suggests that the model is underfitting.
For K in the range 5 to 10, we see that this is the region where the difference between the test and
train accuracies are the minimum which is a good range for the hyperparameter K . Above K =
10, we see that as K increases the difference in accuracy between train and test also increases
suggesting that the model is overfitting!

*Predictive performance:*
We have taken the approach of normalizing and standardizing the data using grid search to find
the optimal value for the hyperparameters. For normalized data,we found the accuracy on the test
data to be 92% and train data as 100%. This indicates that the model is overfitting. Also for the
standardized data, the accuracy on test is 95% and train is 100%. The model here is also overfitting.
Since the accuracy is better, we choose the latter.

● Model Goodness:
The confusion matrix for the final model with an accuracy of 95% is given below.


<img width="382" alt="image" src="https://github.com/p-saraswat/Breast_Cancer_Classification/assets/121529081/1ad9a0cb-701a-4428-8c21-3035bacc1106">








