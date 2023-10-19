# AWS CodeDeploy

<img src="">

CodeDeploy is a deployment service that automates application deployments to Amazon EC2 instances, on-premises instances, serverless Lambda functions, or Amazon ECS services.

You can deploy a nearly unlimited variety of application content, including:

    + Code

    + Serverless AWS Lambda functions

    + Web and configuration files

    + Executables

    + Packages

    + Scripts

    + Multimedia files

+ CodeDeploy can deploy application content that runs on a server and is stored in Amazon S3 buckets, GitHub repositories, or Bitbucket repositories. 

+ CodeDeploy can also deploy a serverless Lambda function. You do not need to make changes to your existing code before you can use CodeDeploy. 

CodeDeploy makes it easier for you to:

    + Rapidly release new features.

    + Update AWS Lambda function versions.

    + Avoid downtime during application deployment.

    + Handle the complexity of updating your applications, without many of the risks associated with error-prone manual deployments.

+ CodeDeploy works with various systems for configuration management, source control, continuous integration, continuous delivery, and continuous deployment.

## Benefits of CodeDeploy

    1. Server, serverless, and container applications
    
    2. Automated deployments
    
    3. Minimize downtime
    
    4. Stop and roll back
    
    5. Centralized control
    
    6. Easy to adopt
    
    7. Concurrent deployments

## CodeDeploy Compute Platforms

CodeDeploy is able to deploy applications to three compute platforms:

      1. EC2/On-Premises
    
      2. AWS Lambda
    
      3. Amazon ECS 


## CodeDeploy Deployment Types

CodeDeploy provides two deployment type options:

    1. In-place deployment

The application on each instance in the deployment group is stopped, the latest application revision is installed, and  the new version of the application is started and validated.

     2. Blue/green deployment

The behavior of your deployment depends on which compute platform you use:

      i. **Blue/green on an EC2/On-Premises compute platform**

+ The instances in a deployment group (the original environment) are replaced by a different set of instances (the replacement environment).

      ii. **Blue/green on an AWS Lambda or Amazon ECS compute platform**

+ Traffic is shifted in increments according to a canary, linear, or all-at-once deployment configuration.

      iii. **Blue/green deployments through AWS CloudFormation**

+ Traffic is shifted from your current resources to your updated resources as part of an AWS CloudFormation stack update. Currently, only ECS blue/green deployments are supported

















































































































































