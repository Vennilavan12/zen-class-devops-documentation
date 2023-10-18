# AWS CodePipeline

<img src="">

AWS CodePipeline is a continuous delivery service you can use to model, visualize, and automate the steps required to release your software. You can quickly model and configure the different stages of a software release process. CodePipeline automates the steps required to release your software changes continuously. 

## Benefits

1. Pipeline as Code

2. Managed by AWS

3. Workflow modeling

4. AWS service integration

## Features

1. Continuous Delivery

+ a software development methodology where the release process is automated. Every software change is automatically built, tested, and deployed to production.

+ Before the final push to production, a person, an automated test, or a business rule decides when the final push should occur.

+ Although every successful software change can be immediately released to production with continuous delivery, not all changes need to be released right away.

<img src="">

2. Continuous Integration

+ a software development practice where members of a team use a version control system and frequently integrate their work to the same location, such as a main branch. 

+ Each change is built and verified to detect integration errors as quickly as possible.
  
+ Continuous integration is focused on automatically building and testing code, as compared to continuous delivery, which automates the entire software release process up to production.

<img src="">

## Workflow of Codepipeline

+ when developers commit changes to a source repository, CodePipeline automatically detects the changes. Those changes are built, and if any tests are configured, those tests are run.

+ After the tests are complete, the built code is deployed to staging servers for testing. From the staging server, CodePipeline runs more tests, such as integration or load tests.

+ Upon the successful completion of those tests, and after a manual approval action that was added to the pipeline is approved, CodePipeline deploys the tested and approved code to production instance

<img src="">

## Codepipeline Concepts

Modeling and configuring your automated release process is easier if you understand the concepts and terms used in AWS CodePipeline.

### Pipeline Terms





















