# ServerLess-Architecture
Serverless Architecture
Project 2: Serverless Web Application with AWS Lambda

Introduction

AWS Lambda allows you to build highly scalable serverless applications without managing backend infrastructure. This project will demonstrate how to build a fully functional API-driven web application using AWS Lambda, API Gateway, and DynamoDB.

Architecture Overview

AWS Lambda: Executes backend logic.

Amazon API Gateway: Routes HTTP requests.

DynamoDB: Stores application data in a NoSQL database.

IAM Roles: Provides access control.

Step-by-Step Implementation

Create a Lambda Function:

Navigate to AWS Lambda > Create Function.

Select Author from scratch, provide a function name, and choose Python 3.8+ as the runtime.

Use the following function:

import json
def lambda_handler(event, context):
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from AWS Lambda!')
    }

Deploy the Function:

Package the function in a zip file and upload it:

zip function.zip lambda_function.py
aws lambda create-function --function-name myLambdaFunction --runtime python3.8 --role execution-role --handler lambda_function.lambda_handler --zip-file fileb://function.zip

Create an API Gateway to Trigger Lambda:

Open API Gateway > Create API.

Choose HTTP API and integrate with the Lambda function.

Test Your API Endpoint:

Copy the API Gateway URL and call the endpoint:

curl -X GET https://your-api-id.execute-api.us-east-1.amazonaws.com/

Achievement & Business Use Case

Achievement: Successfully implemented a backend-less API with automatic scaling and zero server management.

Use Case: Best suited for mobile applications, IoT backends, and lightweight web applications.

