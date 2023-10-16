# AWS CodeCommit

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc1.png">

+ AWS CodeCommit is a version control service hosted by Amazon Web Services that you can use to privately store and manage assets (such as documents, source code, and binary files) in the cloud.

+ CodeCommit is a secure, highly scalable, managed source control service that hosts private Git repositories.

+ CodeCommit eliminates the need for you to manage your own source control system or worry about scaling its infrastructure.

+ It supports the standard functionality of Git, so it works seamlessly with your existing Git-based tools.

## Benefits

1. Store code securely

2. Work collaboratively on code

3. Easily scale your version control projects

4. Store anything, anytime

5. Integrate with other AWS and third-party services

6. Easily migrate files from other remote repositories

7. Use the Git tools

## What is Git

+ Git is a DevOps tool used for source code management. 

+ It is a free and open-source version control system used to handle small to very large projects efficiently. 

+ Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc2.png">

## How does CodeCommit work?

+ CodeCommit is familiar to users of Git-based repositories, but even those unfamiliar should find the transition to CodeCommit relatively simple. 

+ CodeCommit provides a console for the easy creation of repositories and the listing of existing repositories and branches.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc4.png">

## Repository

+ A repository is the fundamental version control object in CodeCommit.

+ It's where you securely store code and files for your project. It also stores your project history, from the first commit through the latest changes. You can share your repository with other users so you can work together on a project.

+ If you add AWS tags to repositories, you can set up notifications so that repository users receive email about events (for example, another user commenting on code). You can also change the default settings for your repository, browse its contents, and more.

+ You can create triggers for your repository so that code pushes or other events trigger actions, such as emails or code functions. You can even configure a repository on your local computer (a local repo) to push your changes to more than one repository.

## Files

+ In CodeCommit, a file is a version-controlled, self-contained piece of information available to you and other users of the repository and branch where the file is stored.
  
+ You can organize your repository files with a directory structure, just as you would on a computer. Unlike your computer, CodeCommit automatically tracks every change to a file.

+ You can compare versions of a file and store different versions of a file in different repository branches.

+ To add or edit a file in a repository, you can use a Git client. You can also use the CodeCommit console, the AWS CLI, or the CodeCommit API.

## Pull Request

+ A pull request is the primary way you and other repository users can review, comment on, and merge code changes from one branch to another.

+ You can use pull requests to collaboratively review code changes for minor changes or fixes, major feature additions, or new versions of your released software.

## Approval Rule

+ You can create approval rules for pull requests. To automatically apply approval rules to some or all of the pull requests created in repositories, use approval rule templates.

+ Approval rule templates help you customize your development workflows across repositories so that different branches have appropriate levels of approvals and control.

+ You can define different rules for production and development branches. Those rules are applied every time a pull request that matches the rule conditions is created.

+ You can associate an approval rule template with one or more repositories in the AWS Region where they are created.

## Commits

+ Commits are snapshots of the contents and changes to the contents of your repository.

+ Every time a user commits and pushes a change, that information is saved and stored.

+ So, too, is information that includes who committed the change, the date and time of the commit, and the changes made as part of the commit.

+ You can also add tags to commits, to easily identify specific commits

In CodeCommit, you can:

  + Review commits.

  + View the history of commits in a graph.

  + Compare a commit to its parent or to another specifier.

  + Add comments to your commits and reply to comments made by others.

## Branches

+ In Git, branches are pointers or references to a commit. In development, they're a convenient way to organize your work. You can use branches to separate work on a new or different version of files without affecting work in other branches. 

+ You can use branches to develop new features, store a specific version of your project from a particular commit, and more.

+ When you create your first commit, a default branch is created for you. This default branch is the one used as the base or default branch in local repositories (repos) when users clone the repository.

+ The name of that default branch varies depending on how you create your first commit.

+ If you add the first file to your repository by using the CodeCommit console, the AWS CLI, or one of the SDKs, the name of that default branch is main.

+ In CodeCommit, you can change the default branch for your repository. You can also create and delete branches and view details about a branch.

## How to create Codecommit

**Step 1:** Login into AWS management console

**Step 2:** In AWS management console search for codecommit service

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc3.png">

**Step 3:** Click create repository

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc5.png">

+ Give repository name and click create 

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc6.png">

+ Once the repository created we use any one of the methods to store the repo locally.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc7.png">

+ You can also create files using CodecommitUI.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc8.png">


<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc.png">


<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cc.png">










































