---
layout: post
title: E-Commerce Recommendation System - Exploring the Balance between Consumer and Business Interest - Part I
---
Can we build a recommendation system that balances consumer and business interest?

The rise of ecommerce over the past few years has offered convenience for consumers who are now shopping online more than ever before. In this market, the number of users is predicted to reach 4,877.0 M by 2025 (ECommerce - worldwide: Statista market forecast 2022). E-commerce websites now house more products than could fit in a physical location often resulting in information overload for the consumer who is unable to easily sort through options. For businesses, the continuous growth of e-commerce markets has turned attention to how innovative technology and data science can aid in bridging the gap between consumer behaviors and the purchasing of products and/or services online with the intent to increase profit (Longo, 2018). One strategy for accomplishing this has been the usage of machine learning, more specifically recommendation systems.

Recommendation systems are a common type of machine learning-based applications which are often used in businesses to increase engagement with users on their platform. Using this kind of system, industries have revolutionized their online platforms by learning the behavior of their consumers and providing them with what they need. In order to develop such models, consumer data is often collected throughout the user experience lifecycle on websites. There lies the concerns with business ethics and privacy. Mixed reviews on whether data collection imposes harm or benefits consumers is an ongoing topic amongst industry leaders (Ivanova, 2017). For example, there have been rising concerns about preserving user privacy when using these systems since more and more personal information, from demographic to behavioral, is included in the data collection process (Sweeney, 2000). Therefore it is important for both businesses and consumers to understand how different user information contributes to the recommendation outcome. Since consumer data have been the general building blocks of any recommendation system especially with regards to increasing accuracy, an important problem to consider is the balance between consumer and business interest.

The goal of this project is to investigate the usage of consumer data for recommendation systems in addition to product data, and its effect on accuracy and overall business impact with an aim to identify and suggest modeling strategies that offer maximum consumer privacy without comprising the business.

The project was a collaborative effort with Yongwen Zhuang, Alexus Mack, Ke Xu, Esha Srivastava, Ritika Wadhwa, and Zhihui Zhang. It served as a final project submission for the DS4A 2022 Summer Fellowship Program. See the code to the project [here](https://github.com/gloriahwoang/EcommerceRecSys).

# About the Dataset

The link to the Kaggle dataset is [here](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations).

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/dataset_1.png" width="400" style="border: #ddd 1px solid;">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/dataset_2.png" width="400" style="border: #ddd 1px solid;">
</div>


# Exploratory Data Analysis

## Articles EDA

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/index_group_name.png" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/perceivedcolorvalue.png" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/perceivedcolormaster.png" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/graphicalappearance.png" width="300">
</div>

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/indexgroupname_garmentgroupname.png" width="600">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/indexgroupname_productgroupname.png" width="600">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/indexgroupname_perceivedcolorvalue.png" width="600">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/top10inventory.png" width="600">
</div>

## Customers EDA

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/age.png" width="500">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/fashionnewsfreq.png" width="600">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/clubmemberstatus.png" width="600">
</div>

## Transactions EDA

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/top10indexsold.png" width="600">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/top10prodgroupsold.png" width="600">
</div>


<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/monthlytrans.png" width="600">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/dailytrans.png" width="600">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/weekdaytrans.png" width="600">
</div>

# Feature Engineering

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/featureengineering.png" width="400" style="border: #ddd 1px solid;">
</div>

# Algorithm & Modeling

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/models.png" width="400" style="border: #ddd 1px solid;">
</div>

# Model 3

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/model3.png" width="400" style="border: #ddd 1px solid;">
</div>

# Results: Balancing Consumer & Business Interest

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/results.png" width="400" style="border: #ddd 1px solid;">
</div>