# AWS CodePipeline

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/CP1.png">

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

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cp3.png">

2. Continuous Integration

+ a software development practice where members of a team use a version control system and frequently integrate their work to the same location, such as a main branch. 

+ Each change is built and verified to detect integration errors as quickly as possible.
  
+ Continuous integration is focused on automatically building and testing code, as compared to continuous delivery, which automates the entire software release process up to production.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cp2.png">

## Workflow of Codepipeline

+ when developers commit changes to a source repository, CodePipeline automatically detects the changes. Those changes are built, and if any tests are configured, those tests are run.

+ After the tests are complete, the built code is deployed to staging servers for testing. From the staging server, CodePipeline runs more tests, such as integration or load tests.

+ Upon the successful completion of those tests, and after a manual approval action that was added to the pipeline is approved, CodePipeline deploys the tested and approved code to production instance

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/PipelineFlow.png">

## Codepipeline Concepts

Modeling and configuring your automated release process is easier if you understand the concepts and terms used in AWS CodePipeline.

### Pipeline Terms

        Pipelines

            + Stages

            + Actions

        Pipeline executions

            + Stopped executions

            + Failed executions

            + Superseded executions

        Stage executions

        Action executions

        Transitions

        Artifacts

        Source revisions

## Pipelines

A pipeline is a workflow construct that describes how software changes go through a release process. Each pipeline is made up of a series of stages.

## Stages

+ A stage is a logical unit you can use to isolate an environment and to limit the number of concurrent changes in that environment.

+ Each stage contains actions that are performed on the application artifacts.

+ Your source code is an example of an artifact.

+ A stage might be a build stage, where the source code is built and tests are run. It can also be a deployment stage, where code is deployed to runtime environments.

+ Each stage is made up of a series of serial or parallel actions.

## Actions

+ An action is a set of operations performed on application code and configured so that the actions run in the pipeline at a specified point.

+ This can include things like a source action from a code change, an action for deploying the application to instances, and so on.

+ Valid CodePipeline action types are

        source

        build

        test

        deploy

        approval

        invoke

## Pipeline executions

+ An execution is a set of changes released by a pipeline. Each pipeline execution is unique and has its own ID.

+ An execution corresponds to a set of changes, such as a merged commit or a manual release of the latest commit.

+ Two executions can release the same set of changes at different times.

+ While a pipeline can process multiple executions at the same time, a pipeline stage processes only one execution at a time. To do this, a stage is locked while it processes an execution.

+ Two pipeline executions can't occupy the same stage at the same time. The execution waiting to enter the occupied stage is referred to an inbound execution.

+ An inbound execution can still fail, be superseded, or be manually stopped. Pipeline executions traverse pipeline stages in order.

+ Valid statuses for pipelines are 

     InProgress

      Stopping

      Stopped

      Succeeded

      Superseded

      Failed

### Stopped executions

+ The pipeline execution can be stopped manually so that the in-progress pipeline execution does not continue through the pipeline.

+ If stopped manually, a pipeline execution shows a Stopping status until it is completely stopped. 

There are two ways to stop a pipeline execution:

      + Stop and wait

      + Stop and abandon

### Failed executions

+ If an execution fails, it stops and does not completely traverse the pipeline. Its status is **FAILED** status and the stage is unlocked.

+ A more recent execution can catch up and enter the unlocked stage and lock it.

+ You can retry a failed execution unless the failed execution has been superseded or is not retryable.

### Superseded executions

+ An execution can be superseded by a more recent execution at a certain point, which is the point between stages.

+ If an execution is waiting to enter a locked stage, a more recent execution might catch up and supersede it.

+ The newer execution now waits for the stage to unlock, and the superseded execution stops with a **SUPERSEDED** status.

+ When a pipeline execution is superseded, the execution is stopped and does not completely traverse the pipeline.


## Stage executions

+ A stage execution is the process of completing all of the actions within a stage. 

  Valid statuses for stages are

      InProgress

      Stopping

      Stopped

      Succeeded

      Failed 

##

























































