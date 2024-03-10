![Git](osnovnye-git-komandy.png)
 
 
 #  Working with Git

## 1. Installation Git

+ Installation Git for Windows,Linux,MAC : https://git-scm.com/downloads
- Install with default settings. When using Git for the first time, you need to introduce yourself. To do this, enter 2 commands in the terminal:
**git config --global user.name "your name"**
**git config --global user.email "your email address"**
## 2. Git version
-  Checking if Git is installed
In the terminal, run the command `git --version`. 
If git is installed, a message will appear with information about the program version, otherwise there will be an error message
## 3. Initialize the repository:
- If you don't already have a Git repository, open your project folder in VS Code, then use a terminal to run the _git init_ command. This will create a local Git repository in your project.
## 4. Writing changes to the repository
 - Adding files to the index:
Before committing changes, you must add the changed files to the Git index. To do this, use the git add command. For example, to add all changed files to the index, run:
         git add .
Instead of `.` you can specify the specific files you want to add.
## 5. Viewing commit histories
- To view the commit history of a Git repository, you can use the git log command. Here's how to use it:
Open terminal:
Open a terminal or command prompt on your computer.
Go to your repository directory:
Use the `cd` command to change to your project directory. For example:
    cd path_to_your_project
## 6. Moving between saves (commits)
- In Git, to move between saves (commits) in your repository, you can use:
 
      git checkout <branch_name>
This command will switch your working directory to the latest commit on the selected branch.

# Working with remote repositories

## 1.  Creating an account on the repository hosting platform:

The first step in working with remote repositories is to create an account on your chosen repository hosting platform. The most popular platforms are GitHub, GitLab and Bitbucket. In our case, this is [Git Hub](https://github.com)

- Go to the site and create a new repository.
- During the creation process, specify the repository name, its description and other settings, if necessary.
- Getting the remote repository URL:

- Once the repository is created, you will receive a URL that you will need to link to it.
- The URL will look something like this: - https://github.com/username/repository.git where username is your username on the platform and repository is the name of your repository.
- Access settings:

- On the hosting platform, you can control access to your repository by setting read and write permissions for other users.
It's important to keep track of permissions so that only the right people can view and change your code.
Once this step is completed, your remote repository is ready to accept changes from the local repository, as well as provide access to other developers for collaboration.



### 2. Adding a remote repository

- Open a terminal or command prompt on your computer 
Navigate on the command line to the directory of your local repository. This is usually done using the `cd` (change directory) command.

- Adding a remote repository:

Use the `git remote add` command to add a link to a remote repository. The command format looks like this:

        
     git remote add <name> <remote repository URL>

        
Here `<name>` is the alias you give to the remote repository. The words `origin`, `upstream` are usually used, but you can choose any other name that is convenient for you.

`<Remote repository URL>` is the address of the remote repository that you received in the previous step when creating the remote repository.

Example: 
    
For example, if you want to add a remote repository on GitHub named "origin", then the command would look like this:

    git remote add origin https://github.com/username/repository.git

- Here `https://github.com/username/repository.git` is the URL of your remote repository.

- after running this command, your local repository will be linked to the specified remote repository under the name you choose (for example, "origin"). You will now be able to push changes from the local repository to the remote repository and receive changes from the remote repository.

## 3. Pushing changes to a remote repository:

- Commit changes

Before pushing changes to the remote repository, make sure you have made all the necessary changes to your local repository and committed those changes using the git commit command.
Committing is committing changes to your repository's history with a message about what has changed.

- Submitting changes:

Use the git push command to push your commits to a remote repository. The command format looks like this:


     git push <remote repository name> <your branch name>


remote repository name is the name of the remote repository that you have linked your local repository to (eg origin).
<your branch name> is the name of the branch from which you want to push changes to the remote repository.
Example:

For example, to push changes from the local main branch to a remote repository named origin, use the following command:

    git push origin main

- Authentication:

During the git push command, you may be asked to provide credentials for your remote repository. This occurs if the remote repository requires authentication, which is often the case when working with online platforms like GitHub or GitLab.

- Result:

After a successful git push, the changes from your local branch will be pushed to the remote repository and will be available to other developers working on that repository.

This step is important for collaboration and synchronization of changes between your local repository and a remote repository that can be used by your team or developer community.

## 4. Getting changes from a remote repository

- Git pull command:

The `git pull` command is used to pull changes from a remote repository and merge them into your local repository.
Command usage:

Open a terminal or command prompt in your local repository directory.
Use the `git pull` command followed by the name of the remote repository and the branch you want to pull changes from.

    git pull <remote repository name> <your branch name>

  `<remote repository name>` is the name of the remote repository, for example origin.

  `<your branch name>` is the name of your local branch from which you want to pull changes.

  Example:

For example, to pull changes from the main branch on the remote origin repository, use the following command:

     git pull origin main

- Result:

The `git pull` command will download changes from the remote repository to your local repository and automatically merge the changes if necessary.
If there are merge conflicts, you may need to resolve them manually.

- Alternative way:

You can also use the `git fetch` command to fetch changes from a remote repository without automatic merging. You can then decide which changes to integrate with your local repository using Git commands such as `git merge` or `git rebase`.

Checking status:

After running the `git pull` command, you can check the status of your local repository using the git status command to ensure that all changes have been successfully pulled and merged.

This step is important to ensure that your local repository remains in sync with changes made to the remote repository by other project members.

## 5.  Updating the local repository with the received changes:

To update the local repository and push the resulting changes from the remote repository, use the command git pull [remote repository name] [branch]. This document takes changes from the remote repository and automatically links them to your local branch. This allows you to stay abreast of changes and work with real data.

## 6. Pushing changes to a remote repository:

To push your local changes to a remote repository, use the command git push [remote repository name] [branch]. This will allow you to upload all your work to a specified branch of the remote repository. After running this command, your changes will be available to other project participants and will be saved to the remote repository.

# Pull Request

## Pull Request is a mechanism used by version control systems such as GitHub or GitLab to propose changes to a project's code. This mechanism allows developers to make changes on a separate branch and submit a pull request to the main branch of the project. Working with Pull Requests simplifies the process of collaborating on a project and ensures better and safer changes.

## To create a Pull Request, follow these steps:

1. Create a new branch: Before you start working on your changes, make sure you are on the latest version of the project's master branch. Then create a new branch for your changes using the command `git branch [new branch name]`.

2. Make the necessary changes: Work on making changes, fixes or adding new functionality in your local branch.

3. Commit your changes: Once you're done, commit your changes using the command git commit -m "Describe your changes."

4. Push changes to the remote repository: Push your local branch with the changes to the remote repository using the command git push origin [name of your branch].

5. Create a Pull Request: Go to a version control platform (such as GitHub), find your newly created branch and click the "Create Pull Request" button. Fill out the required information about your change request, describing the nature of the changes, the initiators, and the test scenarios.

6. Discussion and code review: other project participants can view your Pull Request, leave comments, ask questions and suggest corrections. After making the necessary modifications to your code, you can upload the changes to the remote repository again.

7. Merging Changes: Once your Pull Request has been discussed and approved by the project administrator, changes can be merged into the main branch of the project, which means your code is included in the main body of the project.

Pull Request is a powerful tool for organizing work on a project in a team, providing transparency, code discussion and the ability to make quality changes.  [more here](https://rustycrate.ru/%D1%80%D1%83%D0%BA%D0%BE%D0%B2%D0%BE%D0%B4%D1%81%D1%82%D0%B2%D0%B0/2016/03/07/contributing.html)


 



