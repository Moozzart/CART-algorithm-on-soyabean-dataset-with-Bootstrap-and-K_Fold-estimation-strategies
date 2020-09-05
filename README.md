# CART-algorithm-on-soyabean-dataset-with-Bootstrap-and-K_Fold-estimation-strategies
## Objectives
-Build a classifier model based on the CART algorithm

-Verify your classifier using both the k-fold and Bootstrap estimation strategies

-Report the performance measure in terms of Confusion matrix, Predictive accuracy, F1-score, Precision and Recall in each case of your verification

-Obtain a ROC curve comparing the different classifiers you have built during your model validation

## Decision Classifier Theory
-Classification and regression trees is a term used to describe a decision tree algorithms that are used for classification and regression learning tasks. 

-The Classification and Regression Tree methodology, also known as the CART was introduced in 1984 by Leo Breiman, Jerome Friedman, Richard Olshen and Charles Stone.
Decision tree algorithms are nothing but if-else statements that can be used to predict a result based on data.
It can be used for regression as well as classification task

## K-Fold Cross Validation
-Cross-validation is a resampling procedure used to evaluate machine learning models on a limited data sample.

-The procedure has a single parameter called k that refers to the number of groups that a given data sample is to be split into. As such, the procedure is often called k-fold cross-validation. When a specific value for k is chosen, it may be used in place of k in the reference to the model, such as k=10 becoming 10-fold cross-validation.

-I’ve chosen K  values by selecting the best k value from 1-20 because we can compare their results directly for the selection of k- value.

## Bootstrap Algorithm
-The Bootstrap method is a variation of the repeated version of the Random sampling method. The method suggests the sampling of training records with replacement.
Each time a record is selected for the training set, is put back into the original pool of records, so that it is equally likely to be redrawn in the next run.

-In other words, the Bootstrap method samples the given data set uniformly with replacement.

## Implementation of Code
-First we implemented a code without the use of the library's, the steps were as follows:

   -Firstly we cleaned the data with the mode values of the remaining data in the respective columns along with creating the categorical variable(0-19) for the classes
   
   -Then we chose those features which had correlation coefficient with respect to the output >=0.1

   -Then we ran our decision tree model on this data

   -And looped over the k values from 1-20, upon which we got the best f-score of 0.41 for k=15

   -Now we calculated the precision, recall and made the confusion matrix for each iteration
   
-Secondly we implemented the same model by using the libraries as well

   -So, we first imported all the useful packages
   
  -Then we chose classifier to be a Decision Tree Classifier with criterion=’entropy’ and random state=0

  -Then we split our data into train and test and fitted them on our classifier

  -Then we calculated the Confusion matrix, classification report and accuracy score along with the tpr(true positive rate) and fpr(false positive rate) values for the 19 classes by looping it through 0-19.
  
  -Here we got f-score of 89 percent and 55 percent accuracy which more than our model that we did by coding it, it may happen sometimes since it is difficult to tune some 
parameters of the model in raw code

## Experimental Result
-In the first code the best results were obtained by the k value of 15

-In the second code we had to use libraries, though that’s not included in the  first code that i sent you

-Tpr, Fpr and probability scores are calculated on the basis of the testing data on our classifier

SOME OF THE FEATURES GIVEN WERE REMOVED, THE ONLY FEATURES WHICH WERE KEPT IN THE DATA WERE:

'Date','plantstand','precip','temp','hail','areadamage','severity','plant growth','halo','marg','size','leafmild','stem','lodging','intdiscolor','sclerotia','fruitpods','fruitspots','seed','moldgrowth','seeddiscolor','seed size','shriveling','class'.

HERE ‘CLASS’ IS THE OUTPUT VARIABLE AND REST ARE THE INPUT VARIABLES. 


