# HOSTING-WEB-APP-IN-CLOUD

## Overview
Servies used in the project: 

![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/ec90bb5e-0ac7-422b-a147-598b965f2cc4)

- AWS Amplify enables frontend web and mobile developers to quickly and easily build full-stack applications on AWS. Amplify provides two services: Amplify Hosting and Amplify Studio.
- AWS Lambda is a compute service that lets you run code without provisioning or managing servers. Lambda runs code on a high-availability compute infrastructure and performs all of the administration of the compute resources, including      server and operating system maintenance, capacity provisioning and automatic scaling, and logging. With Lambda, we only need to do supply your code in one of the language runtimes that Lambda supports.
- Amazon API Gateway is an AWS service for creating, publishing, maintaining, monitoring, and securing REST, HTTP, and WebSocket APIs at any scale. API developers can create APIs that access AWS or other web services, as well as data       
  stored in the AWS Cloud.
- Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. With DynamoDB, you can create database tables that can store and retrieve any amount of data and serve 
  any level of request traffic.
- AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. With IAM, you can centrally manage permissions that control which AWS resources users can access.

  ## Description
  **FUN WITH NUMBERS** is the basic web app written in HTML. User will provide the number whose square is to be given as the output. AWS Lambda is used to implement the math functionality.
  When user enters the number and click the button 'square', we need to find the square of the number. Inorder to do the computation, we need to trigger the Lambda function using an API 
  generated using AWS API Gateway. The result of the computation will be stored in the AWS Dynamodb. AWS IAM is used to assign required permission for doing operations on the table.

  ## Step 1: Hosting web app using AWS Amplify
  - Go to AWS Amplify in the console.
  - Choose 'host your web app' option.
  - Choose appropriate option to upload your code. I'm going with 'deploy without git provider'.
  - Provide an app name and env name, then upload the code (only zip folder is accepltable). Then save and deploy. For any updates to the web app, you can keep on uploading the updated code.
  - You will get a domain where the app is deployed.
 
  Below given is my sample web app and the workflow.
  
  ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/0cd8637c-49b3-4e87-9e1d-cadef59cb5c3)
  ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/7b9a49ca-1449-414d-a436-e963100b2b0d)
  ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/824ea72e-911b-488b-b8a6-1181fc7055e5)
  ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/324bff3b-31d5-496c-aa64-b9dc848547c8)
  ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/fc29362b-a561-40ec-a8f1-3faf86a37a8a)

  ## Step 2: Adding the math functionality using AWS Lambda
  - Go to AWS Lambda in the console.
  - Choose 'create function' and select 'author from scratch'.
  - Give function name, required runtime env (my case: Python) and create the function.
  - Write the lambda function in the section provided and deploy the changes.
  - Then configure the test event (a test case to run the code) and test it.
 
    ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/af8c2261-deaa-4666-bdfd-6d1bf36d710c)
    ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/ec9a35ad-95fc-401d-9546-be5c5fd10b2c)
    ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/50bfd2c2-ad0e-4c16-8366-dd8a9ad588c4)
    ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/3e62655c-d793-45f8-803c-821ae8d0c65f)
    ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/c61f7e3d-943d-43ec-ab2f-c0366e02d1e9)
    ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/e2bc1f9a-6f2b-40a9-9eff-69604a9a89b2)
    ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/90215bbc-4b2c-4de7-9c86-00d9dd3d1dbe)

    ## Step 3: Using AWS API Gateway to invoke the math functionality
    - Go to AWS API Gateway in the console.
    - Choose REST API and click build.
    - Select 'new API', give API name and create API.
    - From the sidebar, select resources and generate method.
    - Give the method type (GET,POST...), integration type (AWS Lambda), lambda function name and create method.
    - Deploy the API and test it.
    - API will be visible in the stages section.
   
      ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/d8cfe3d8-3875-4cb4-bc15-5bf62b6ab461)
      ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/a1f6ee44-2350-48e6-9203-116ced2cf235)
      ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/13883bbb-914a-4c54-9d9a-7868de687e40)
      ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/6177e531-58fe-482d-8936-44a07f483f04)
      ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/ae0c7d61-e08a-440c-bd5e-681e6b7ecc84)
      ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/8b2cb4bf-821b-4e29-9c51-c200e6bc6d78)
      ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/68f840a8-62d6-4be5-ade9-402b3e0a4de6)
      ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/52dd05f9-bace-443e-aea1-37767dbd1056)

      ## Step 4: Incorporating database AWS Dynamodb and giving permissions using AWS IAM
      - Go to AWS Dynamodb in the console.
      - Create table by entering table name and partion key (ID), we will get the database ARN.
      - Now assign permissions to perform operations on database, to the role that was automatically generally while using AWS Lambda.
      - Go to AWS Lambda, move to permission and click the role specified and add permissions.
      - Review permissions and create it.
      - Now update the lambda function, inorder to store the result in the table created.
      - Deploy the changes and test the function.
      - Result of the computation will get stored in the database.
      - Go to explore items under the tables section in Dynamodb to find the result of computation.
     
        ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/3853587b-fee9-48e9-9428-5f807dde01ec)
        ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/51988a0c-7280-43ae-b0f2-f02d93b68996)
        ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/967ef418-f14e-4fdd-8b74-e92c89dfff08)
        ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/1c281ab2-7ea4-4781-a67a-3c987a3a77d4)
        ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/8e216254-8ebb-4147-821b-bba39f3cbbdb)
        ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/b9cb1fe2-de4a-4ac3-bd82-876350b2cbde)
        ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/c9385afa-e0d6-437f-9632-7e49cf03bf7f)
     
        ## Final Step
        - Use the API generated, in the HTML code to invoke the math function when button 'square' is clicked.

          ![image](https://github.com/AthullyaR/HOSTING-WEB-APP-IN-CLOUD/assets/78737460/7544c243-3b73-4f32-8d8b-5907c349faa8)

       
      
     
      
        




















  

  

  
  
