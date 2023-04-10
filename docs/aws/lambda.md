---
layout: home
parent: AWS
title: Lambda
---

# AWS Lambda

AWS Lambda is a serverless computing service offered by Amazon Web Services (AWS). 

It allows you to run code in response to events without having to manage servers or infrastructure. With AWS Lambda, you can write code in a variety of languages (such as Python, Node.js, or Java), upload it to AWS Lambda, and then run it in response to events triggered by other AWS services or custom events.

## How does AWS Lambda work?

AWS Lambda works by creating "functions" that contain your code and deploying them to AWS Lambda. 

Each function is triggered by an event, such as an incoming API request, a file upload to Amazon S3, or a message on an Amazon Simple Notification Service (SNS) topic. When an event occurs, AWS Lambda automatically provisions the necessary computing resources and runs your code. 

Once the code finishes executing, the resources are released, making it a very cost-effective solution for event-driven workloads.

## How to use AWS Lambda

Here are some tips for using AWS Lambda effectively:

1. **Choose the right trigger**: AWS Lambda supports many different event sources, including S3, DynamoDB, Kinesis, and more. Choose the trigger that makes the most sense for your use case. For example, if you want to process data as soon as it's uploaded to S3, you can configure S3 to trigger a Lambda function whenever a new object is uploaded.

2. **Optimize your code**: Since you pay for the amount of compute time your function uses, it's important to optimize your code to run as efficiently as possible. This might include using caching, minimizing the number of API requests, and optimizing your database queries.

3. **Set appropriate timeouts**: AWS Lambda functions are limited to a maximum runtime of 15 minutes. Make sure you set an appropriate timeout value for your function to ensure it has enough time to complete its work.

4. **Use environment variables**: You can use environment variables in your Lambda function to store configuration data, API keys, and other sensitive information. This makes it easy to manage your configuration and keep your secrets secure.

5. **Monitor your functions**: AWS Lambda integrates with many different monitoring and logging services, such as Amazon CloudWatch and AWS X-Ray. Use these services to monitor your functions and gain visibility into their performance and behavior.

## API

You can use AWS Lambda with API Gateway to receive HTTP requests. API Gateway is a fully managed service that makes it easy to create, deploy, and manage APIs for your AWS Lambda functions.

Here's how you can set up an AWS Lambda function to receive HTTP requests using API Gateway:

1. **Create an API**: Create a new API Gateway API by navigating to the API Gateway console in the AWS Management Console. Choose "REST API" and then "New API".

2. **Create a resource**: Create a new resource in your API by choosing "Create Resource". This will create a new URL path that clients can use to access your API.

3. **Create a method**: Create a new HTTP method for your resource by choosing "Create Method" and selecting the appropriate HTTP method (such as GET, POST, or PUT).

4. **Integrate with AWS Lambda**: Choose "Lambda Function" as the integration type and select the AWS Lambda function that you want to use to handle the request.

5. **Deploy your API**: Deploy your API by choosing "Deploy API". This will create a new deployment of your API that clients can access.

Once you've completed these steps, clients can access your API by sending HTTP requests to the URL provided by API Gateway. API Gateway will handle the incoming requests and forward them to your AWS Lambda function for processing. Your AWS Lambda function should be configured to receive input from API Gateway using the event object provided by AWS Lambda.

By using API Gateway with AWS Lambda, you can build scalable and reliable HTTP APIs that automatically scale to handle large volumes of traffic.

## Sample

This function uses the lambda_handler method as the entry point for the AWS Lambda function. The event parameter contains the input data for the function, which includes the HTTP method, request body, and headers. The context parameter contains information about the runtime environment for the function.

The function uses a case statement to handle different HTTP methods (such as GET and POST) and returns a response based on the input data. In this example, the function returns a JSON response with a message that depends on the HTTP method and request data.

To use this function with API Gateway, you would configure API Gateway to pass the incoming HTTP request to this function as an event. The function would then return a response that API Gateway would forward to the client.

```ruby
require 'json'

def lambda_handler(event:, context:)
  method = event['httpMethod']
  body = event['body']
  headers = event['headers']
  
  # Process the request based on the HTTP method
  case method
  when 'GET'
    # Handle GET requests
    response = {
      statusCode: 200,
      body: JSON.generate({ message: 'Hello, World!' })
    }
  when 'POST'
    # Handle POST requests
    if body.nil?
      response = {
        statusCode: 400,
        body: JSON.generate({ error: 'Missing request body' })
      }
    else
      # Process the request body
      data = JSON.parse(body)
      
      # Perform some action based on the request data
      response_data = { message: "Hello, #{data['name']}!" }
      
      response = {
        statusCode: 200,
        body: JSON.generate(response_data)
      }
    end
  else
    # Return an error for unsupported HTTP methods
    response = {
      statusCode: 405,
      body: JSON.generate({ error: 'Method not allowed' })
    }
  end
  
  # Add headers to the response
  response['headers'] = headers
  
  # Return the response
  response
end
```

## Response streaming

Now you can flush changes to the network socket as soon as it is available and it will be written to the client socket.

AWS Lambda streaming can be used for a variety of real-time data processing tasks, such as data transformation, filtering, aggregation, and enrichment. It is particularly useful for applications that require low-latency processing of large volumes of data, such as real-time analytics, fraud detection, and log processing.

```javascript
exports.handler = awslambda.streamifyResponse(
    async (event, responseStream, context) => {
        responseStream.setContentType(“text/plain”);
        responseStream.write(“Hello, world!”);
        responseStream.end();
    }
);
```
