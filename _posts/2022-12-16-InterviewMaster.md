---
layout: post
title: InterviewMaster - App for Organizing Your Job Interviews
---

The job searching process can become tedious. Many candidates choose to have an excel sheet that summarizes all of their applications, but some may also choose not to have any tracking system at all. With that, some some may forget that he applied to the same company a month ago!

InterviewMaster allows candidates to automatically monitor changes in their candidacy. You can simply give the app permission/access to your Gmail account and it will automatically gather all the job application/status/process information for you! It is fast, simple, and convenient.

This project was a collaborative effort with Aaron Zhao. It served as a final project for the class _Cloud Computing and Big Data with AWS_ at Columbia University. See the code to the project [here](https://github.com/gloriahwoang/InterviewMaster). See also a **Youtube demo** of the project [here](https://youtu.be/PcSSIGiSaiw).

## The Architecture

The figure below shows the architecture diagram of InterviewMaster. There are several main components to this architecture:

Cognito

S3

API Gateway

Lambdas

DynamoDB

SES

And there are several supporting components to the architecture:

- Code Build
- Code Pipeline
- Cloudwatch

The following sections will describe these components in detail.

<div class="img-container">
    <iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="740" height="400" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FcndPKEkiuBd03N5jXP7c7Q%2FArchitecture%3Fnode-id%3D0%253A1%26t%3DQ3OMbTfIGM0KXoe0-1" allowfullscreen></iframe>
</div>

#### Cognito

Cognito was used to add user sign-up and sign-in features and user control access to InterviewMaster. The user receives a second verification email when he/she signs up. This second verification comes from SES to verify the domain. InterviewMaster will then use the email address provided to extract email content information to start organizing the users’ job application statuses.

<div class="img-container">
    <br><img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/login-signup.png" width="550">
    <figcaption>Login and Signup Page</figcaption><br>
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/verification.png" width="550">
    <figcaption>Cognito and SES Verification</figcaption>
</div>

#### S3

Two S3 buckets are supporting this project:

- B1 - 6998finalproject-frontend
- B2 - 6998finalproject-emails

The website is hosted on B1. The application was made with React JS and Node JS. B1 holds all the front-end code. B2, on the other hand, holds the incoming emails of the users signed up with InterviewMaster.

#### API Gateway

API Gateway consists of several methods:

- /login GET
- /setup PUT
- /update PUT

The /setup PUT method connects LF1 with the front-end after the user signs up to PUT the user’s email address to SES and send the SES verification email back to the user.

The /login GET method connects LF3 with front-end after the user successfully logs in to fetch the interview information stored in DynamoDB.

The /update PUT method connects LF4 with front-end to enable the user to modify his/her existing interview information or save new interview information.

#### Lambdas

There are four lambdas in this project:

- LF1 - 6998finalproject-login
- LF2 - 6998finalproject-scrape
- LF3 - 6998finalproject-fetchinterviewdata
- LF4 - 6998finalproject-uploadinterviewdata

LF1 is responsible for sending the SES verification email to the new user. This is to verify the new domain within SES. Once verified, all the incoming emails of the user are stored in the S3 bucket B2. LF2 is then triggered to analyze the email content and extract the interview information, such as company name, date, location, etc. Then the extracted information is put into a DynamoDB table. When the user logs in, LF3 is triggered to fetch the interview information of the user from the DynamoDB table to the front-end. The user is able to modify or even add new interview information manually. When he/she clicks the save button, LF4 is triggered to update the existing data or append new data to the DynamoDB table.

#### DynamoDB

A Dynamo DB table is used to contain users’ interview information (6998finalprojuserinterview1).

Both partition key and sort key are specified while creating the table (‘6998finalprojuserinterview1’). The partition key {useremail: user’s email address} is used by LF 2, 3 and 4 to interact with DynamoDB and store specific emails for specific users. The attribute {insertAtTimeStamp} is set as the sort key which is called by LF4 while updating users' interview data. If the secondary sort key is not present by the front-end, it would be difficult for the lambda function and DynamoDB to identify the interview data that is being modified.

#### SES

With AWS Simple Email Service, the domains are verified and all the emails received from the domains are sent to the S3 bucket (B2).

#### Code Build

Once "npm run build" is run and pushed to Github, Code Pipeline is initiated, and once our source picks up the changes, Code Build starts to build our application and continue down the pipeline.

#### Code Pipeline

Code Pipeline was used for continuous delivery. With Code Pipeline, it made teamwork even easier. It automated our release pipelines for fast updates and helped our team to focus on development.

#### CloudWatch

CloudWatch is a must have for any application development with AWS. With CloudWatch, we were able to debug our code and continue development.

## Wireframing

Below is the wireframing of the project from the very beginning of our development planning.

<div class="img-container">
    <iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="740" height="400" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FTzpT8GwAd0PpCSnx7AQKTo%2FWireframe-%2526-Prototype%3Ft%3DGUnql9cKS2RozNfi-1" allowfullscreen></iframe>
</div>

## Key Designs and Features

#### My Interviews Page

Once the user logs in for the first time, there will not be any data existing as the application can only track incoming email data from the time the user signed up.

As new interview emails come in, InterviewMaster automatically updates the dashboard for the user. The user is able to edit the interview information in case lambda was not successfully able to scrape the information with 100% accuracy. The user is also able to add new interview information manually if there is an interview information that is not existent in their emails.

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/interviewfeature.png" width="550">
    <figcaption>Left: When user logs in for the first time; Right: Sample current user</figcaption><br>
</div>

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/cognito-dynamodb.png" width="550">
    <figcaption>Left: Manage users with Cognito; Right: DynamoDB Table</figcaption>
</div>

## Further Implementation and Improvements

It was a challenge to learn all the AWS modules involved in this project. There are yet a lot of improvements that can be made for further implementation. Some of these include:

- Improve the ML model in scraping company name, position title, etc. to be more accurate.
- Allow the app to import interview information from existant gmail data instead of only incoming data.
