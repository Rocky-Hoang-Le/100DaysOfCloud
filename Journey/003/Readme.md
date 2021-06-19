# Create an android application with AWS backend

## Introduction

Today I chose to study how to use AWS with android applications since I have had previous experience making android applications and games such as an app to help customers choose their nail technician for a nail salon as well as two game apps.

## Prerequisite

For this project some basic knowledge of java or kotlin is required as that is the programming language for android development. Some knowledge of how to write xml and how to use android studio is also required, and for AWS backend some understanding of how to use AWS Amplify.

## Use Case

![Screenshot](https://i.ibb.co/Yfqpnh1/testcase.png)

Using AWS Amplify I am able to provide a backend that can connect to other AWS services such as S3, lambda, and even DynamoDB to my android application.

## Cloud Research

Doing this project taught me a lot of things. I learned the Kotlin programming language through reading documentations as well as learned I can use it side by side with java for android development. I also learned how AWS can connect with android through API calls and receive and upload to AWS from API calls.

For this project I simplify followed the tutorial on how to setup an AWS backend to an android application from here https://aws.amazon.com/getting-started/hands-on/build-android-app-amplify/. However I didn't just copy and paste everything whenever I was provided a code snippet I made sure to understand the code by examing it and adding comments everywhere so I know exactly what each part of the code is doing. When a part of the code didn't make sense to me either cause of syntax of not knowing what it does exactly I looked up documentation on the matter. A lot of problems came from the code being depreciated or outdated in some way.

## Try yourself

For this project simply follow the guide at https://aws.amazon.com/getting-started/hands-on/build-android-app-amplify/. Although most of it will go smoothly I found when the project got to the part with the auto generated class created by amplify some things had to be editted to work.

![Screenshot](https://i.ibb.co/xCMjF7r/errors.png)

Opening the generated class there will be some errors all of them due to improper paramters. Hovering over the errors will clarify what the problem is, and for most of the errors simply removing the problem argument will fix it. For the isReadOnly line this must be changed to isRequired.

## ☁️ Cloud Outcome

Doing this project allowed me to better understand how I can connect to AWS services using APIs as well as learn how to add a AWS backend to my android apps. I also learned to not blindly follow guides and try to understand each part throughly by examing the code snippets given and seeing how they work. In the end I managed to make a functional android application that can perfrom CRUD operations on the cloud and also have a reusuable amplify backend for any other future android projects.

## Next Steps

Now that I have learned how to use AWS Amplify I would like to try other AWS services and continue learning more on how they all connect and interact with each other.

## Social Proof

[LinkedIn](https://www.linkedin.com/posts/rockyle98_100daysofcloud-android-kotlin-activity-6812047423901364224-5CX7)
