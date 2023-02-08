---
layout: post
title: InterviewMaster - App for Organizing Your Job Interviews
---

The job searching process can become tedious. Many candidates choose to have an excel sheet that summarizes all of their applications, but many also choose not to have any tracking system at all. Therefore, some candidates may even forget that he or she applied to the same company six months ago or even forget to check the status of their application from the specific company’s portal. The worst is when the candidate is in the process of many interviews and forget to send thank you notes, or follow up emails to the ones involved in their application processes. It takes a lot of organization and consistency during this job searching process. InterviewMaster is the application that helps with this organization. Once signed up, InterviewMaster will start to keep track of all your incoming emails and watch out for application statuses in your email. You are also able to manually insert interview information that may have existed before you signed up or insert interviews that the system’s NLP failed to catch.

The project was a collaborative effort with Aaron Zhao. It served as a final project for the class Cloud Computing and Big Data with AWS at Columbia University. See the code to the project [here](https://github.com/gloriahwoang/InterviewMaster). See also a **Youtube demo** of the project [here](https://youtu.be/PcSSIGiSaiw).

## The Architecture

rinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently w

<div class="img-container">
    <iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FcndPKEkiuBd03N5jXP7c7Q%2FArchitecture%3Fnode-id%3D0%253A1%26t%3DQ3OMbTfIGM0KXoe0-1" allowfullscreen></iframe>
</div>

ly five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages

<ul class="IM-list">
  <li>Cognito</li>
  <li>S3 Bucket</li>
  <li>API Gateway</li>
  <li>Lambdas</li>
  <li>Dynamo DB</li>
  <li>SES</li>
</ul>

t was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently wrinter took a galley of type and scrambled it to make a type specimen book. It has survived not only

<ul class="IM-list">
  <li>Code Build</li>
  <li>Code Pipeline</li>
  <li>CloudWatch</li>
</ul>

rinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently wrinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently w

## Wireframing

rinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently w

<div class="img-container">
    <iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FTzpT8GwAd0PpCSnx7AQKTo%2FWireframe-%2526-Prototype%3Ft%3DGUnql9cKS2RozNfi-1" allowfullscreen></iframe>
</div>

## App Overview

#### Home Page

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage-2.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage-3.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage-4.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/homepage-5.png" width="300">
</div>

#### Login Page

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/login.png" width="300">
</div>

#### Sign Up Page

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/signup-1.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/signup-2.png" width="300">
</div>

#### Interviews Page

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/interview-1.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/interview-2.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/interview-3.png" width="300">
</div>

## Key Designs and Features

rinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recen

<div class="img-container">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/verification-1.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/verification-2.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/cognito.png" width="300">
    <img class="center-2" src="https://raw.githubusercontent.com/gloriahwoang/gloriahwoang.github.io/master/images/dynamodb.png" width="300">
</div>

## Further Implementation and Improvements

rinter took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recen
