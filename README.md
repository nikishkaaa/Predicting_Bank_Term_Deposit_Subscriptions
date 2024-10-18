# Bank Marketing Dataset Machine Learning Project
## The Task
The "Bank Marketing Data Set" from the UCI Machine Learning Repository focuses on direct marketing campaigns (phone calls) conducted by a Portuguese bank. The objective is to classify whether a client will subscribe to a term deposit (target variable y). Detailed attribute descriptions can be found at the original UCI URL: https://archive.ics.uci.edu/ml/datasets/Bank+Marketing.
In this project, we develop two classifiers: a decision tree and a random forest, using ROC AUC score as the evaluation metric to compare their performances.

## Approach
We implement two feature engineering strategies: 
Label encoding for the Education variable and one-hot encoding for other categorical fields.
Ordinal encoding for the Education variable along with one-hot encoding for categorical fields.
We create a pipeline that integrates feature engineering and the machine learning model, either a decision tree or a random forest.
  
 ## Pipeline
Pipelines are instrumental in structuring a sequence of operations. This project aims to demonstrate the use of Scikit-learn's pipeline for executing stratified K-fold cross-validation, feature engineering, and fitting a machine learning model in that specific order. Stratified K-fold cross-validation helps mitigate overfitting. We compute the mean training and testing scores for each classifier.

Additionally, we incorporate SMOTE and undersampling into the pipeline to address class imbalance. Specifically, we randomly undersample 50% of the majority class data and oversample 20% of the minority class data. This combined approach significantly reduces class imbalance, enhancing model performance compared to using either method alone.

After fitting the random forest pipeline, we collect the important features from each of the 10 estimators (due to 10-fold stratified cross-validation) and compile them into a dataframe sorted by importance. Using these key features, we can refine the model and recalculate both training and testing accuracy.

A key concept in this project involves adjusting the decision threshold from the default 0.5 to a value that maximizes training and testing accuracy. Given the dataset's imbalance, where 'No' is the predominant prediction, we modify the threshold to better support the model's learning for the 'Yes' class.

## Results
We list only those results where training accuracy and testing accuracy are nearly equal and high enough. 
<table>
  <tr>
    <th rowspan="2"> Classifier</th>
    <th colspan="2">Decision Tree</th>
    <th colspan="2">Logistic Regression</th>
    <th colspan="2">KNN</th>
    <th colspan="2">XGBoost</th>

  </tr>
  <tr>
    <th>Train ROC AUC score </th>
    <th> Test ROC AUC score </th>
    <th>Train ROC AUC score </th>
    <th> Test ROC AUC score </th>
    <th>Train ROC AUC score </th>
     <th> Test ROC AUC score </th>
     <th>Train ROC AUC score </th>
     <th> Test ROC AUC score </th>
      
  </tr>
  <tr>
    <td></td>
    <td> </td>
    <td> </td>
      <td> </td>
    <td> </td>
      <td> </td>
    <td> </td>
      <td> </td>
    <td> </td>
  </tr>
</table>
