# AWS CloudFormation

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cf1.png">

+ AWS CloudFormation is a service that helps you model and set up your AWS resources so that you can spend less time managing those resources and more time focusing on your applications that run in AWS.
  
+ You create a template that describes all the AWS resources that you want (like Amazon EC2 instances or Amazon RDS DB instances), and CloudFormation takes care of provisioning and configuring those resources for you.
   
+ You don't need to individually create and configure AWS resources and figure out what's dependent on what; CloudFormation handles that.

## Benefits 

1. Deployment speed

2. Scaling up

3. Service integration

4. Consistency

5. Security

6. Easy updates

## Cloudformation Concepts

When you use AWS CloudFormation, you work with templates and stacks. You create templates to describe your AWS resources and their properties.

1. Templates

2. Stacks

3. Change sets

## Templates

+ A CloudFormation template is a JSON or YAML formatted text file.

+ You can save these files with any extension, such as .json, .yaml, .template, or .txt.

+ CloudFormation uses these templates as blueprints for building your AWS resources. For example, in a template, you can describe an Amazon EC2 instance, such as the instance type, the AMI ID, block device mappings, and its Amazon EC2 key pair name.

+ Whenever you create a stack, you also specify a template that CloudFormation uses to create whatever you described in the template.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cf3.png">

# Stacks

+ When you use CloudFormation, you manage related resources as a single unit called a stack.

+ You create, update, and delete a collection of resources by creating, updating, and deleting stacks.

+ All the resources in a stack are defined by the stack's CloudFormation template.

+ Suppose you created a template that includes an Auto Scaling group, Elastic Load Balancing load balancer, and an Amazon Relational Database Service (Amazon RDS) database instance.

+ To create those resources, you create a stack by submitting the template that you created, and CloudFormation provisions all those resources for you.

## Change sets

+ If you need to make changes to the running resources in a stack, you update the stack.

+ Before making changes to your resources, you can generate a change set, which is a summary of your proposed changes.

+ Change sets allow you to see how your changes might impact your running resources, especially for critical resources, before implementing them.

### Example

+ if you change the name of an Amazon RDS database instance, CloudFormation will create a new database and delete the old one.

+ You will lose the data in the old database unless you've already backed it up.

+ If you generate a change set, you will see that your change will cause your database to be replaced, and you will be able to plan accordingly before you update your stack.

## How does cloudformation works

+ When creating a stack, AWS CloudFormation makes underlying service calls to AWS to provision and configure your resources.

+ CloudFormation can only perform actions that you have permission to do.

+ For example, to create EC2 instances by using CloudFormation, you need permissions to create instances.

+ You'll need similar permissions to terminate instances when you delete stacks with instances.

+ You use AWS Identity and Access Management (IAM) to manage permissions.

+ The calls that CloudFormation makes are all declared by your template.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cf2.png">

## Template Anatomy

A template is a JSON- or YAML-formatted text file that describes your AWS infrastructure.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cf4.png">

## Format Version

The AWSTemplateFormatVersion section (optional) identifies the capabilities of the template. The latest template format version is 2010-09-09 and is currently the only valid value.

### JSON

    "AWSTemplateFormatVersion" : "2010-09-09"

### YAML 

    AWSTemplateFormatVersion: "2010-09-09"

## Description

+ The Description section (optional) enables you to include comments about your template.

+ The value for the description declaration must be a literal string that is between 0 and 1024 bytes in length

### JSON

    "Description" : "Here are some details about the template."

### YAML 
    
    Description: > Here are some details about the template.

## Metadata

You can use the optional Metadata section to include arbitrary JSON or YAML objects that provide details about the template.

### JSON

    "Metadata" : {
      "Instances" : {"Description" : "Information about the instances"},
      "Databases" : {"Description" : "Information about the databases"}
    }

### YAML 

    Metadata:
      Instances:
        Description: "Information about the instances"
      Databases: 
        Description: "Information about the databases"

### Meta keys

  AWS::CloudFormation::Init

  AWS::CloudFormation::Interface

  AWS::CloudFormation::Designer

## Parameters

Use the optional Parameters section to customize your templates. Parameters enable you to input custom values to your template each time you create or update a stack.

### Example 

declare a parameter named InstanceTypeParameter. This parameter lets you specify the Amazon EC2 instance type for the stack to use when you create or update the stack. Note that InstanceTypeParameter has a default value of t2.micro.

### JSON

    "Parameters" : {
      "ParameterLogicalID" : {
        "Type" : "DataType",
        "ParameterProperty" : "value"
      }
    }
  
### YAML 

    Parameters:
      ParameterLogicalID:
        Type: DataType
        ParameterProperty: value

## Rules

+ The optional Rules section validates a parameter or a combination of parameters passed to a template during a stack creation or stack update. To use template rules, explicitly declare Rules in your template followed by an assertion. 

+ A rule can include a RuleCondition property and must include an Assertions property.

### Rule specific intrinsic functions

To define a rule condition and assertions, use rule-specific intrinsic functions, which are functions that can only be used in the Rules section of a template. You can nest functions, but the final result of a rule condition or assertion must be either true or false.

  Fn::And

  Fn::Contains

  Fn::EachMemberEquals

  Fn::EachMemberIn

  Fn::Equals

  Fn::If

  Fn::Not

  Fn::Or

  Fn::RefAll

  Fn::ValueOf

  Fn::ValueOfAll 

## Mappings

+ The optional Mappings section matches a key to a corresponding set of named values. 

+ For example, if you want to set values based on a region, you can create a mapping that uses the region name as a key and contains the values you want to specify for each specific region. You use the Fn::FindInMap intrinsic function to retrieve values in a map.

## JSON 

<img src="">

## YAML

<img src="">

## Conditions

## Transform

## Resources

## Output
