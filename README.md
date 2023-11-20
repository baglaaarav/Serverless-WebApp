## Create a serverless web application .

####  This is a serverless Web application that uses number of AWS servies. This AWS serverless web application offers an HTML interface for users to input their pickup location, interacting with a backend RESTful web service for request submission. The application includes user registration and login capabilities.

#### Resources used in this project:
- IAM
- CodeCommit
- API Gateway
- Dynamo DB
- Amplify
- cognito
- Lambda
- AWS CLI
- AWS SES

### Project Architecture:
https://github.com/baglaaarav/Serverless-WebApp/blob/27d547205972ade8bddd26657a80b90fc5696162/diagram.png

### What I did:

I began by creating a new user in AWS Identity and Access Management (IAM) with the required permissions. Subsequently, I generated access keys for this user and configured the AWS Command Line Interface (CLI) using aws configure.

Afterward, I established a CodeCommit repository in AWS to store the code for my static website. I then cloned this repository to my local machine, added the static website code, committed the changes, and pushed them to AWS CodeCommit.

For hosting the website, I leveraged AWS Amplify, selecting the "host web app" option for streamlined deployment.

To enable user authentication, I set up an Amazon Cognito user pool, ensuring email verification through  AWS SES. Integration into the website was accomplished by configuring the client ID and user ID, providing a sign-in option for users.

Moving to the backend, I created a DynamoDB table and an IAM role for Lambda to access and perform 'put' operations in DynamoDB, facilitated by an inline policy.

A Lambda function was then developed to insert items into the DynamoDB table, establishing efficient communication between the website and the backend.

For connecting Lambda to Cognito through an API Gateway, I created an API Gateway. This gateway invokes the Lambda function whenever a request to put an item in the DynamoDB table is made.

This systematic configuration of IAM, AWS CodeCommit, AWS Amplify, AWS SES, Amazon Cognito, Lambda, DynamoDB, and API Gateway resulted in a comprehensive architecture for my static website, complete with robust backend functionalities.
