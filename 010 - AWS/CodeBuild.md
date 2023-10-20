# AWS CodeBuild

<img src="">

+ AWS CodeBuild is a fully managed build service in the cloud.

+ CodeBuild compiles your source code, runs unit tests, and produces artifacts that are ready to deploy.

+ CodeBuild eliminates the need to provision, manage, and scale your own build servers.

+ It provides prepackaged build environments for popular programming languages and build tools such as Apache Maven, Gradle, and more.

+ You can also customize build environments in CodeBuild to use your own build tools. CodeBuild scales automatically to meet peak build requests.

## Benefits

1. **Fully managed** – CodeBuild eliminates the need to set up, patch, update, and manage your own build servers.

2. **On demand** – CodeBuild scales on demand to meet your build needs. You pay only for the number of build minutes you consume.

3. **Out of the box** – CodeBuild provides preconfigured build environments for the most popular programming languages. All you need to do is point to your build script to start your first build.

## CodeBuild Workflow

<img src="">

+ You can use the AWS CodeBuild or AWS CodePipeline console to run CodeBuild.

+ You can also automate the running of CodeBuild by using the AWS Command Line Interface (AWS CLI) or the AWS SDKs.

+ you can add CodeBuild as a build or test action to the build or test stage of a pipeline in AWS CodePipeline.

+ AWS CodePipeline is a continuous delivery service that you can use to model, visualize, and automate the steps required to release your code.

+ This includes building your code. A pipeline is a workflow construct that describes how code changes go through a release process.

<img src="">

## How CodeBuild works

+ As input, you must provide CodeBuild with a build project.

### Build Project

+ A build project includes information about how to run a build, including where to get the source code, which build environment to use, which build commands to run, and where to store the build output.

## Build Environment

+ A build environment represents a combination of operating system, programming language runtime, and tools that CodeBuild uses to run a build.

+ CodeBuild uses the build project to create the build environment.

+ CodeBuild downloads the source code into the build environment and then uses the build specification (buildspec), as defined in the build project or included directly in the source code.

###  Buildspec

+ A buildspec is a collection of build commands and related settings, in YAML format, that CodeBuild uses to run a build.

+ If there is any build output, the build environment uploads its output to an S3 bucket. The build environment can also perform tasks that you specify in the buildspec (for example, sending build notifications to an Amazon SNS topic).

+ While the build is running, the build environment sends information to CodeBuild and Amazon CloudWatch Logs.

+ While the build is running, you can use the AWS CodeBuild console, AWS CLI, or AWS SDKs to get summarized build information from CodeBuild and detailed build information from Amazon CloudWatch Logs.

+ If you use AWS CodePipeline to run builds, you can get limited build information from CodePipeline.








































