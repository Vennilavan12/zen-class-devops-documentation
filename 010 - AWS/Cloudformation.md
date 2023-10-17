# AWS CloudFormation

<img src="">

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
+
+ CloudFormation uses these templates as blueprints for building your AWS resources. For example, in a template, you can describe an Amazon EC2 instance, such as the instance type, the AMI ID, block device mappings, and its Amazon EC2 key pair name.
+
+ Whenever you create a stack, you also specify a template that CloudFormation uses to create whatever you described in the template.

<img src="">

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

<img src="">

## Template Anatomy
























