# ServerLess-Architecture
Serverless Architecture
Project 2: Serverless Web Application with AWS Lambda

Introduction

AWS Lambda allows you to build scalable serverless applications without managing backend servers.

Architecture Overview

AWS Lambda: Executes backend logic.

Amazon API Gateway: Routes HTTP requests.

DynamoDB: Stores data for the app.

Step-by-Step Implementation

Create a Lambda Function:

import json
def lambda_handler(event, context):
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from AWS Lambda!')
    }

Deploy the Function:

aws lambda create-function --function-name myLambdaFunction --runtime python3.8 --role execution-role --handler lambda_function.lambda_handler --zip-file fileb://function.zip

Create an API Gateway to Trigger Lambda:

Go to API Gateway > Create API

Choose HTTP API and link it to Lambda.

Result

Your function is now accessible via an API endpoint.

