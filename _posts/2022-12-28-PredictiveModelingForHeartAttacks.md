---
layout: post
title: Predictive Modeling for Heart Attacks
---

According to the Center for Disease Control and Prevention, heart disease is a leading cause of death within the United States [1]. Within heart diseases, heart attacks are one of the most common. In the United States, a person has a heart attack every forty seconds [2]. The goal is to take preventative measures to avoid heart attacks. In order to take preventative measures, features that lead to the cause of heart attacks must be identified.

This project intends to explore various models that can sufficiently predict if a person is prone to ha eart attack or not. Categorical and continuous features will be used to identify a binary output of whether someone has a heart attack, where 0 denotes the normal state of no heart attack and 1 denotes the abnormal state of heart attack. The categorical variables in the models are number of major vessels, chest pain, fasting blood sugar, and thallium stress test results. The continuous variables are age, maximum heart rate, resting blood pressure, cholesterol level, and previous peak.

The project was a collaborative effort with Andrea Lin, Joan Akibode, Sanaa Mouzahir, and Minh Nguyen. It served as a final project for the class Data Science in Mechanical Systems at Columbia University. See the code to the project [here](https://github.com/gloriahwoang/Predictive-Modeling-for-Heart-Attacks).

## How does the data look?

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

**Categorical Variables**

<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/sex-distribution.png" alt="Sex" width="300">
<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/caa-distribution.png" alt="Number of Major Vessels" width="300">
<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/chest-pain-distribution.png" alt="Chest Pain" width="300">
<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/fasting-blood-sugar-distribution.png" alt="Fasting Blood Sugar" width="300">
<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/thall.png" alt="Thalium Stress Test Result" width="300">

**Continuous Variables**

<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/age-distribution.png" alt="Age" width="300">
<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/max-heart-rate.png" alt="Maximum Heart Rate" width="300">
<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/resting-bp.png" alt="Resting Blood Pressure" width="300">
<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/cholesterol-distribution.png" alt="Cholesterol" width="300">
<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/previous-peak.png" alt="Previous Peak" width="300">

**Target Variable**

<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/heartattack.png" alt="Heart Attack">

### Feature Selection

<img align="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/correlation.png" alt="Correlation">

## References

[1] Centers for Disease Control and Prevention. Underlying Cause of Death, 1999–2018. CDC WONDER Online Database. Atlanta, GA: Centers for Disease Control and Prevention; 2018. Accessed March 12, 2020.

[2] Fryar CD, Chen T-C, Li X. Prevalence of uncontrolled risk factors for cardiovascular disease: United States, 1999–2010 pdf icon[PDF-494K]. NCHS data brief, no. 103. Hyattsville, MD: National Center for Health Statistics; 2012. Accessed May 9, 2019.
