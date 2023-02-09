---
layout: post
title: InterviewMaster - App for Organizing Your Job Interviews
---

The job searching process can become tedious. Many candidates choose to have an excel sheet that summarizes all of their applications, but some may also choose not to have any tracking system at all. With that, some some may forget that he applied to the same company a month ago!

InterviewMaster allows candidates to automatically monitor changes in their candidacy. You can simply give the app permission/access to your Gmail account and it will automatically gather all the job application/status/process information for you! It is fast, simple, and convenient.

This project was a collaborative effort with Aaron Zhao. It served as a final project for the class "Cloud Computing and Big Data with AWS" at Columbia University. See the code to the project [here](https://github.com/gloriahwoang/InterviewMaster). See also a **Youtube demo** of the project [here](https://youtu.be/PcSSIGiSaiw).

## The Architecture

The figure below shows the architecture diagram of InterviewMaster. There are several main components to this architecture:

- Cognito
- S3
- API Gateway
- Lambdas
- Dynamo DB
- SES

And there are several supporting components to the architecture:

- Code Build
- Code Pipeline
- Cloudwatch

The following sections will describe these components in detail.

<div class="img-container">
    <iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FcndPKEkiuBd03N5jXP7c7Q%2FArchitecture%3Fnode-id%3D0%253A1%26t%3DQ3OMbTfIGM0KXoe0-1" allowfullscreen></iframe>
</div>

#### Cognito

Cognito was used to add user sign-up and sign-in features and control access to InterviewMaster. With Cognito, sign-up verifications are sent to the user and once verified, the user can sign-in and start using the app. A username, an email address, and a password are needed to sign-up. The user receives a second verification email when he/she signs up. This second verification comes from SES to verify the domain. InterviewMaster will then use the email address provided to extract email content information to start organizing the users’ job application status.

## Wireframing

rinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently w

<div class="img-container">
    <iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FTzpT8GwAd0PpCSnx7AQKTo%2FWireframe-%2526-Prototype%3Ft%3DGUnql9cKS2RozNfi-1" allowfullscreen></iframe>
</div>

## App Overview

#### Home Page

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage-2.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage-3.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage-4.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage-5.png" width="300">
</div>

#### Login Page

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/login.png" width="300">
</div>

#### Sign Up Page

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/signup-1.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/signup-2.png" width="300">
</div>

#### Interviews Page

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/interview-1.png" width="300">
</div>

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/interview-2.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/interview-3.png" width="300">
</div>

## Key Designs and Features

rinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recen

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recen

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/verification-1.jpg" width="300">
</div>

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recen

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/verification-2.jpg" width="300">
</div>

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recen

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/cognito.png" width="300">
</div>

but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recen

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/dynamodb.png" width="300">
</div>

## Further Implementation and Improvements

rinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recen
