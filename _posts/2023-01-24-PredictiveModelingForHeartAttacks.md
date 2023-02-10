---
layout: post
title: Predictive Modeling for Heart Attacks
---

According to the Center for Disease Control and Prevention, heart disease is a leading cause of death within the United States [1]. Within heart diseases, heart attacks are one of the most common. In the United States, a person has a heart attack every forty seconds [2]. What are the preventive measures to avoid heart attacks? In order to address this question, we must identify features that lead to the cause of herat attacks.

This project intends to explore various models that can predict if a person is prone to a heart attack or not. This project was a collaborative effort with Andrea Lin, Joan Akibode, Sanaa Mouzahir, and Minh Nguyen. It served as a final project for the class _Data Science in Mechanical Systems_ at Columbia University. See the code to the project [here](https://github.com/gloriahwoang/Predictive-Modeling-for-Heart-Attacks).

## How does the data look?

Below is a sample of the dataset, consisting of the first 5 rows.

!["Data-Sample"]({{ site.baseurl }}/images/data-first 5-rows.png)

### Data Dictionary

| **Column Name**     | **Description**                                                                                             |
| :------------------ | :---------------------------------------------------------------------------------------------------------- |
| age                 | age of the patient                                                                                          |
| sex                 | gender of the patient                                                                                       |
| chest pain          | chest pain type: 0 = typical angina, 1 = atypical angina, 2 = non-anginal pain, 3 = asymptomatic            |
| resting BP          | resting blood prressure (in mm Hg)                                                                          |
| chol                | cholestoral in mg/dl fetched via BMI sensor                                                                 |
| fasting blood sug   | fasting blood sugar > 120 mg/dl : 1 = True, 2 = False                                                       |
| resting elec result | resting electrocardiographic results: 0 = normal, 1 = ST-T wave normality, 2 = left ventricular hypertrophy |
| max heart rate      | maximum heart rate achieved                                                                                 |
| previous peak       | previous peak                                                                                               |
| slp                 | slope                                                                                                       |
| caa                 | number of major vessels                                                                                     |
| thall               | thalium stress test result                                                                                  |
| exercise            | exercised induced angina : 1 = yes, 0 = no                                                                  |
| output              | target variable (Heart Attack Classification) : 0 = no heart attack, 1 = abnormal state of heart attack     |

### Exploratory Data Analysis

The data was explored through plots and descriptive statistics to better understand how to handle the data as well as to understand the distribution of the data. The data consisted of both categorical and continuous variables to be analyzed.

#### Categorical Variables

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/sex-distribution.png" alt="Sex" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/caa-distribution.png" alt="Number of Major Vessels" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/chest-pain-distribution.png" alt="Chest Pain" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/fasting-blood-sugar-distribution.png" alt="Fasting Blood Sugar" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/thall.png" alt="Thalium Stress Test Result" width="300">
</div>

#### Continuous Variables

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/age-distribution.png" alt="Age" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/max-heart-rate.png" alt="Maximum Heart Rate" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/resting-bp.png" alt="Resting Blood Pressure" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/cholesterol-distribution.png" alt="Cholesterol" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/previous-peak.png" alt="Previous Peak" width="300">
</div>

#### Target Variable

Ensuring a balanced class split is important because most modeling algorithms were designed for even class splits. If there is an imbalance, this must be handled accordingly with specialized techniques. The plot below shows that our target variable had an even class split of 0, denoting the normal state of no heart attack, and 1, denoting an abnormal state of having a heart attack.

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/heartattack.png" alt="Heart Attack" width="300">
</div>

## Which features will be used to predict the target variable?

The plot below shows a correlation matrix, representing the weight of correlation measured with Spearman’s coefficient.

The features most correlated with heart attack were chest pain, maximum heart rate, exercise and thallium stress test results. Some of these correlation relationships are intuitive, but other results, such as the lack of correlation between age and heart attack and between cholesterol and heart attack, were surprising. Aside from the necessity of removing collinearity, this further reinforces the value of correlation analysis.

When two variables were highly correlated with each other, the feature more correlated with the output was kept. Ultimately, the variables that were dropped were: exercise, sex, slope, and resting electrocardiographic results.

The data was split into 80% for the training set and 20% for the testing set.

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/correlation.png" alt="Correlation" width="500">
</div>

## Which model predicts with the highest accuracy?

Accuracy was measured in terms the proportion of true results among the total number of cases examined. Three machine learning models were trained with the data. Overall, the logistic regression model yielded the best results.

### Logistic Regression

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/logistic-regression-score.jpg" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/logistic-regression.png" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/logistic-regression-roc.jpg" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
</div>

Two trials of logistic regression were performed, one using the Statsmodel library and the other using Scikit-learn library with bootstrapping introduced in an attempt to increase prediction accuracy. Bootstrapping is a method of repeatedly selecting from the original data a set of randomly shuffled samples to perform logistic regression on, and then the mean, standard error and distribution of the combined results can be retrieved. However, the accuracy score was higher for the model without bootstrapping.

### Support Vector Machine

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/svm-score.jpg" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/svm.png" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/svm-roc.jpg" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
</div>

The flexibility of SVM allows for nonlinear classification, and kernels of different dimensions are used for this purpose. In the case of this data, a linear kernel is chosen for simplicity. The model can also be tuned with the hyperparameters C, which affects the strength of the regularization, consequently controlling the margin of the classifier. A cross validation grid-search from Scikit-Learn is performed to find the optimal value for C, chosen from a range of 1 to 10, with 5 being the final optimal value chosen. The same method was used to find the optimal value for the parameter "gamma" from a range of select number. 0.05 was the optimal gamma in the result.

### Random Forest

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/randomforest-score.jpg" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/randomforest.png" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/randomforest-roc.jpg" width="210" style="border: #ddd 1px solid; margin-right: 15px;">
</div>

In Random Forest modeling, various hyperparameters associated with formation of the decision trees as well as bagging strategies are available. In this model, the maximum depth of the trees and the number of estimators (i.e., number of trees) are the parameters that were explored. A cross validation grid search is performed to find the optimal values for these parameters. The optimal number of parameters are chosen from [12,13,14,15], and the optimal maximum depth is chosen from [3,4,5,6]. From those options, the optimal values for the number of estimators and maximum depth were 13 and 4, respectively.

## Can the accuracy of our models be improved?

In the first model used to train the data, logistic regression was the obvious first choice for this binary classification problem. The resulting accuracy score of 87% is strong but there is room for improvement. The limitation of this dataset may be the number of samples, since logistic regression prefers larger sample sizes. Due to the limited number of samples, the attempt to introduce bagging to the logistic regression model did not yield results significantly different from the simple model. With few other hyperparameters to tune in logistic regression, the next step was to explore other algorithms for binary classification. Thus, the SVM and Random Forest models were pursued.

In this initial exploration of models, the full flexibility of SVM and random forest was not explored, thus the results for these two models may be further improved with a thorough examination of hyperparameter tuning. This could include the consideration of more hyperparameters along with the use of different methods of hyperparameter optimization. In this work, cross validation grid search was used, which takes a set of predefined hyperparameter inputs to search from. Other methods such as random search may perhaps uncover better parameters for enhanced model performance.

Additionally, obtaining more data can also help improve the model accuracy and explore other areas that may affect the higher risk in heart diseases. For example, data about the life-style of a person, such as diet, average sleep hours, etc. can be obtained to see a different point of view of the study. Other important data such as weights and family history that were left out may also be helpful in improving the prediction of heart diseases.

## References

[1] Centers for Disease Control and Prevention. Underlying Cause of Death, 1999–2018. CDC WONDER Online Database. Atlanta, GA: Centers for Disease Control and Prevention; 2018. Accessed March 12, 2020.

[2] Fryar CD, Chen T-C, Li X. Prevalence of uncontrolled risk factors for cardiovascular disease: United States, 1999–2010 pdf icon[PDF-494K]. NCHS data brief, no. 103. Hyattsville, MD: National Center for Health Statistics; 2012. Accessed May 9, 2019.
