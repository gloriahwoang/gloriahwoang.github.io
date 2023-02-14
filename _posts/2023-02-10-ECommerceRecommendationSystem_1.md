---
layout: post
title: E-Commerce Recommendation System - Exploring the Balance between Consumer and Business Interest - Part I
---
Can we build a recommendation system that balances consumer and business interest?

Ecommerce has grown exponentially during the past few years, offering convenience for consumers who are now shopping mostly online. Business are now striving to become more competitive by learning more about consumer behaviors in relation to the purchasing of their products. The main objectives for these companies is to maximize profit. One strategy for this has been the use of recommendation systems, a common type of machine learing based application. In order to develop these systems, consumer data is often collected. Because of this, there has been rising concerns about user privacy. Can we build a recommendation system that balances consumer and business interest? This is important because the use of consumer data is becoming more advanced. Both business and consumers should be aware of its implications. We aim to identify and suggest modeling strategies for future use that offer maximum consumer privacy without compromising the business.

The project was a collaborative effort with Yongwen Zhuang, Alexus Mack, Ke Xu, Esha Srivastava, Ritika Wadhwa, and Zhihui Zhang. It served as a final project submission for the DS4A 2022 Summer Fellowship Program. See the code to the project [here](https://github.com/gloriahwoang/EcommerceRecSys).

# About the Dataset

The link to the Kaggle dataset is [here](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations).

The dataset is as follows: articles metadata, customers metadata, and transactions records. The dataset comes from the years 2018-2020 and consists of 37 columns and more than 100,000 records.

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/dataset_1.png" width="640">
</div>

Below are the variables that are included in each assets:

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/dataset_2.png" width="640">
</div>


# Exploratory Data Analysis

How does the data look like? To explore this, an exploratory data analysis was performed on the dataset.
## Articles EDA

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/index_group_name.png" width="300">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/perceivedcolorvalue.png" width="300" padding=20><br>
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

Shown below is the age distribution of H&M customers. The age of customers ranges from 16 to 99, with an average age of 36, and customers aging mainly in the 20s and between 45 and 60.

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/age.png" width="500">
</div>

H&M sends fashion news and also has a club member. From the following plots, we find that most customers have an active club member status but majority of them do not receive fashion news, and only 470,000 members receive fashion news regularly.

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/clubmemberstatus_fashionnewsfreq.png" width="600">
</div>

## Transactions EDA

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/top10indexsold.png" width="600">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/top10prodgroupsold.png" width="600">
</div>


<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/monthlytrans.png" width="500">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/dailytrans.png" width="500">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/weekdaytrans.png" width="500">
</div>

# Feature Engineering

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/featureengineering.png" width="640">
</div>

# Algorithm & Modeling

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/models.png" width="640">
</div>

# Model 3

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/model3.png" width="640">
</div>

# Results: Balancing Consumer & Business Interest

<div class="img-container">
    <img class="center" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/results.png" width="640">
</div>

<br>
<br>