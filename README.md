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

# Step 4 - Starting Your Environment

The best way to start any project is to pull your latest changes from GIT down onto you device. This will ensure that you are working with the latest version of your code. To do this run the command: 

```shell
git pull origin main
```

This command will pull the last commit from the origin. However, be sure to check what your branch is. On my mac it seems that the better command is: 

```shell
git pull origin HEAD
```
## Python Set Up
First, we need to make sure that we have configured out dependencies. In this case, our requirements file requires us to install setuptools wheel and upgrade -r

```shell
python3 -m pip install --upgrade pip setuptools wheel
python3 -m pip install --upgrade -r requirements.txt
```
The command -r requirements.txt is a great command as it updates our virtual environment withatever dependencies are contained in our requirements.txt file. This is a much much faster way of checking in dependencies when we run our venv. Using our requirement file will enable us to keep our dependencies in order. 

## Running Python
First, we must initialize our virtual environment. Without a virtual environment running, python has no place to run our device. To start a virtual environemnt. We run a hard to remember command:

```shell
source .venv/bin/activate
python3 demo_script.py
```

This code tells the terminal to run in the .venv note that if we give our environment a different name when we run the initial command to create our .venv that we can actually have multiple virtual environments under different names in the same file. But, if a new name is added then it must be added to the .gitignore file. 

To create a new environment we can simple run: 

```shell
python3 -m venv .venv
```

This string of code will create a viritual environment under .venv if we change the .venv to .virtualenvironment that would create an environment under a different name. By adding python3 at the beginning we are telling the computer to interepret the virtual environment as python3. 

## Running Jupyter Notebooks
A jupyter notebook is a place to store code in a document. It's useful for writing up a narrative of a coding project that includes runnable examples of the code. We use the .ipynb extension to specify a jupyter notebook. We can run the notebook by creating a venv as before. We just need to make sure that our notebook is running in the appropriate .venv. This can be done by selecting the kernel option. If we have already ran:

```shell
python3 -m venv .venv
```
Then it is not strictly necessary for us to run it again
Only to run the notebook we simply run it in the text editor

We can skip this if the virtual environemnt is already running. In general, if the kernel fails to recognize that we have the appropriate extensions installed all we have to do is run: 

```shell
python3 -m pip install --upgrade -r requirements.txt
```

This simple script will reupdate our venv with any extensions or libraries we needed. 

# Final Note
Be sure to always check which terminal you are running in and which python environment is being used. Running directly from the python home directory can potentially lead to conflicts such as: duplicate packages or installs of python versions. It's always best to run python in the virtual environment. You can activate your venv using the shell: 

```shell
source .venv/bin/activate
```

And you can deactivate it at any time by typing: 

```shell
deactivate
```
