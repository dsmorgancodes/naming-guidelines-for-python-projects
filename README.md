# naming-guidelines-for-python-projects
Provides naming guidelines for python projects

# Step 1 - Starting GIT From Scratch
First, initialize GIT by creating a repository from scratch. Give it a name, a brief description and also a be sure to check the box for the .readme file. This will add a project description to your workflow. Hit create and reload the repository in a new window. You will need the URL of the repository to connect GIT to VS Code. 

# Step 2 Add .gitigore and requirements.txt 
During this step we will add two files that help GIT and future users of our code understand how to use our code. 

## What is .gitignore? 
.gitignore is a txt file that tells git which parts of the project it does not need track. This is useful to prevent us from leaking sensitive data and other information that we may not want to expose in our repository. 

## What is requirements.txt
requirement.txt is a txt file that contains the requirements for our project. It often tells us which version of python is best, or which tooling we will need to have installed to run the code. 

# Step 3 - Push and Pull Requests
In this step we run some basic git commands that push and pull code from git. 

## Pull Requests
In most cases, the first step needed is a git pull. This is done by running the following commands in the terminal:

```shell
git pull origin main
```

But once this is run initially. It is usually enough to just run. Git assumes that we are pulling from the origin and from the main branch because that was our last request. 

```shell
git pull
```
Once we have made this initial pull we can review the output for updates and any conflicts. If we find conflicts, we should resolve these before we proceed. 

## Push Requests
A push request pushes our code to our github repository for future changes. A push consists of three important parts: 

### Add
The command git add . is used to stage our changes. When we use the "." command we are staging our changes for every file in our repository. To do specific changes to specific files we can use the file path of the file or even the folder. This makes it possible for us to stage changes on only a single file or folder of our codebase instead of the whole thing.

```shell
git add .
```

### Commit
The command git commit -m "details of the git commit" tells git to commit the changes in git add to the repository. When we add the -m "content" this adds brief message to our labeled snapshot of what we are about to update. Consider this the final step before execution. 

```shell
commit -m "Added files to repository .gitignore and requirements.txt"
```

### Push
The command git push -u origin main pushes our changes added and then committed to the branch of our choosing. By adding -u we associate the local branch (our file) with the remote branch (the file to push to git). origin is just the standard name of the remote repository. main specifies which branch we are deploying our staged changes to. 

```shell 
git -u origin main
```

## Complete Push Request
A complete push request consist of the above three commands - combined: 

```shell
git add .
git commit -m "Message about this commit"
git push -u origin main
``` 

After your initial push, subsequent pushes run in the same terminal can be shortened to:

```shell
git push
```

The details of your previous push request are remembered and reused. 

# Starting a good enviroment. 
The best way to start any project is to pull your latest changes from GIT down onto you device. This will ensure that you are working with the latest version of your code. To do this run the command: 

```shell
git pull origin main
```

This command will pull the last commit from the origin. 