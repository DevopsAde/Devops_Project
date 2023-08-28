# Documentation For GIT

## This Project shows how to Initialze a Repository, Make Commits, Work with Branches, Collaboration and Remote Repositories & Branch Management and Tagging

## What is Git

Git is a distributed version control system, which essentially solves the problem of sharing source code efficiently and keeping track of changes made to source code.

## INITIALIZING A GIT REPOSITORY

Before initializing a Git Repo first we need to install Git on our local machine.

- [install Git](https://git-scm.com/downloads)

- Now below are the commands used in initalizing a git repo in the command line.

![Alt text](<Initialize a Git repo.png>)

## Making First Commit

In the Image above we successfully created the working directory and initialize the git repository. Before we commit lets really understand what a commit is.

The analogy when you commit, git literally takes a snapshot of the current state of the present repository and saves a copy in the .git folder inside your present working directory.Also, changes can be through adding, modifying or deleting files or text.

Now lets make our first commit by following the following steps below.

![Alt text](<Images/Making your first Commit.png>)

## NOTE

- The -m flag `$ git commit -m "initial commit"` is used to commit message. The commit message is a nice way to provide context about the commit.

## Working with Branches

Git branch is commonly used to develop new feature of any application. Git, basically helps in creating

different copy of the source code. Git is also an important tool for collaboration within remote teams

(developers working from different location). They can make seperate branches while working on the same

 source code. And at the end of the day, coverge their code to one branch.

## Make your first git Branch

- To make a new branch run this command
**`git checkout -b`**
-the -b flag helps you create and change into the new branch
- to make a new branch run this command **`git checkout -b any-name`**

![Alt text](<Create your first git Branch.png>)

## Listing your git Branches

- Use the command below to list the branches on your local git repository

**`git branch`**

![Alt text](<Listing your git Branches.png>)

## Change into an Old Branch

- To navigate into an existing or previous branch use the command below:

**`git checkout <branch-name>`**

![Alt text](<Change into an Old Branch.png>)

## Merging a Branch into another Branch

- In this example below, we are merging two branches Main and Head_quarter, we are basically adding the contenst of Main into Head_quarter.


![Alt text](<Merging a Branch into another Branch.png>)

## Cont

![Alt text](<Merging a Branch into another Branch Cont..png>)

## Deleting a git branch

When a new feature is added to an application, usually this feature branch is deleted when the code must have been tested and merged into a staging or dev environment depending on the branch strategy of the team.

- Git Branch can be deleted with the command below:

**`git branch -d <branch_name>`**

- Also to familiarize with the git command, use the command below.
**`git branch --help`**

## Collaboration and Remote Repositories

- Previously, we discuused that git is used for collaboration among remote teams (developers residing in

 different location). But how can developers work remotely to make changes, adding  and updating on the

 same code base since we currently have our code on our local computer.

- This where github comes in.

## What is Github

Github is a web based platform where git repositories are hosted. By hosting our local git repo on

github, it becomes available to the public internet where anyone can access it. you can also create a

private repositoryas well.

- Remote Teams can now view, update, and make changes to the same repository.

## Creating a Github Account

- Go to this Link and follow this easy steps to download and configure your github account:

- [Alt text](https://github.com/)

- After following all the steps to download and successful account registration. Below is the image:

![Alt text](<GitHub Account Created.png>)

## Creating yoyr First Repository

- Step 1: Click on the New icon in green color

- Step 2: fill out the form by adding a unique repository name

![Alt text](<Create a new repo.png>)

## Pushing your Local git Repository to your Remote github Repository

- Now for friends and developers around the world to contribute to our file or source code, this will

not be possible because it's still stored locally in our local machine. Having created a github account

and github repository previously.

- We will send a copy to our repository in github.

- Step 1: Add a remote repository to the local repository using the command below:

**`$ git remote add origin <link to your github repo>`**

![Alt text](<Pushing your local git repo to remote github repo.png>)

- Step 2: After commiting your changes in your local repo. You push the content to the remote repo using

the command below:

**`$ git push origin <branch name>`**

Note: the word origin refers to your remote repo link

## Cloning Remote Git Repository

Now, after succesfully adding a remote git repository and

pushed into the local repository. Now, other

developers can contribute to our source code.

![Alt text](<Cloning Remote Git Repo.png>)

## Note

 It has always been a best practice to make a local copy of 
 
our source code stored locally in the

machine. And also creates a branch where he can make all modifications.

- To make a local copy of our source code or file, we use the Git clone command.

 **`$ git clone <link to your remote repository>`**

- The git clone command helps in making a copy of the remote repository in our local machine.





**THANK YOU** 




# Documentation For GIT

## This Project shows how to Initialze a Repository, Make Commits, Work with Branches, Collaboration and Remote Repositories & Branch Management and Tagging

## What is Git

Git is a distributed version control system, which essentially solves the problem of sharing source code efficiently and keeping track of changes made to source code.

## INITIALIZING A GIT REPOSITORY

Before initializing a Git Repo first we need to install Git on our local machine.

- [install Git](https://git-scm.com/downloads)

- Now below are the commands used in initalizing a git repo in the command line.

![Alt text](<Initialize a Git repo.png>)

## Making First Commit

In the Image above we successfully created the working directory and initialize the git repository. Before we commit lets really understand what a commit is.

The analogy when you commit, git literally takes a snapshot of the current state of the present repository and saves a copy in the .git folder inside your present working directory.Also, changes can be through adding, modifying or deleting files or text.

Now lets make our first commit by following the following steps below.

![Alt text](<Making your first Commit.png>)

## NOTE

- The -m flag `$ git commit -m "initial commit"` is used to commit message. The commit message is a nice way to provide context about the commit.

## Working with Branches

Git branch is commonly used to develop new feature of any application. Git, basically helps in creating

different copy of the source code. Git is also an important tool for collaboration within remote teams

(developers working from different location). They can make seperate branches while working on the same

 source code. And at the end of the day, coverge their code to one branch.

## Make your first git Branch

- To make a new branch run this command
**`git checkout -b`**
-the -b flag helps you create and change into the new branch
- to make a new branch run this command **`git checkout -b any-name`**

![Alt text](<Create your first git Branch.png>)

## Listing your git Branches

- Use the command below to list the branches on your local git repository

**`git branch`**

![Alt text](<Listing your git Branches.png>)

## Change into an Old Branch

- To navigate into an existing or previous branch use the command below:

**`git checkout <branch-name>`**

![Alt text](<Change into an Old Branch.png>)

## Merging a Branch into another Branch

- In this example below, we are merging two branches Main and Head_quarter, we are basically adding the contenst of Main into Head_quarter.


![Alt text](<Merging a Branch into another Branch.png>)

## Cont

![Alt text](<Merging a Branch into another Branch Cont..png>)

## Deleting a git branch

When a new feature is added to an application, usually this feature branch is deleted when the code must have been tested and merged into a staging or dev environment depending on the branch strategy of the team.

- Git Branch can be deleted with the command below:

**`git branch -d <branch_name>`**

- Also to familiarize with the git command, use the command below.
**`git branch --help`**

## Collaboration and Remote Repositories

- Previously, we discuused that git is used for collaboration among remote teams (developers residing in

 different location). But how can developers work remotely to make changes, adding  and updating on the

 same code base since we currently have our code on our local computer.

- This where github comes in.

## What is Github

Github is a web based platform where git repositories are hosted. By hosting our local git repo on

github, it becomes available to the public internet where anyone can access it. you can also create a

private repositoryas well.

- Remote Teams can now view, update, and make changes to the same repository.

## Creating a Github Account

- Go to this Link and follow this easy steps to download and configure your github account:

- [Alt text](https://github.com/)

- After following all the steps to download and successful account registration. Below is the image:

![Alt text](<GitHub Account Created.png>)

## Creating yoyr First Repository

- Step 1: Click on the New icon in green color

- Step 2: fill out the form by adding a unique repository name

![Alt text](<Create a new repo.png>)

## Pushing your Local git Repository to your Remote github Repository

- Now for friends and developers around the world to contribute to our file or source code, this will

not be possible because it's still stored locally in our local machine. Having created a github account

and github repository previously.

- We will send a copy to our repository in github.

- Step 1: Add a remote repository to the local repository using the command below:

**`$ git remote add origin <link to your github repo>`**

![Alt text](<Pushing your local git repo to remote github repo.png>)

- Step 2: After commiting your changes in your local repo. You push the content to the remote repo using

the command below:

**`$ git push origin <branch name>`**

Note: the word origin refers to your remote repo link

## Cloning Remote Git Repository

Now, after succesfully adding a remote git repository and

pushed into the local repository. Now, other

developers can contribute to our source code.

![Alt text](<Cloning Remote Git Repo.png>)

## Note

 It has always been a best practice to make a local copy of 
 
our source code stored locally in the

machine. And also creates a branch where he can make all modifications.

- To make a local copy of our source code or file, we use the Git clone command.

 **`$ git clone <link to your remote repository>`**

- The git clone command helps in making a copy of the remote repository in our local machine.





**THANK YOU** 




[def]: <Initialize a Git repo.png>