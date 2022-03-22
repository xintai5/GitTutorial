# How to Use Git from the Command Line
For the sake of simplicity, we will be working through a step by step example of how to add small projects to GitHub using command line. This tutorial will also cover the use of stashes, branches, and merging. 

*Throughout this tutorial, the word 'repository' will be referred to as 'repo'. This is complicated comp sci lingo get use to it.*

## Step 1: Create a Local Git Repo 

First, go to the [Github](https://github.com/) website and create an account or login to one if you already have one. Press the '+' drop down menu next to your profile image and select 'New repository'. Next, fill in the 'Repository name' and 'Description (optional)' sections and decide whether or not to make the project public or private.

![Create a new repo](https://user-images.githubusercontent.com/44709545/159394216-5d72ed50-6886-4ada-b9f6-dba4e8811e41.png)

## Step 2: Open Up Command Line

If you have a Mac, open up the Terminal app. If you have Windows, open up cmd.  We now want to go to the directory in the computer that the project is stored in. Use cd to navigate to the local project directory that you want to publish on GitHub. These are the commands:

Mac: `$ cd directory_name_where_project_is`
Windows: `$ cd/directory_name_where_project_is`

## Step 3: Initialize the Local Directory

To initialize our newly created project as a Git repository, use this command in Terminal/cmd: `$ git init`

## Step 4: Add and Commit the Local Repo

To add all the files in the local directory into the local repo, we need to stage all the files in the directory by using this command: `$ git add`

This command stages all the files in the directory, ready for commit.

Next, in order to commit the staged files, use this command: `$ git commit -m "Added a new file"` 

Use a short sentence to help explain what you are committing.

## Step 5: Add the Remote Repo url

In GitHub, copy the remote repo URL that is provided to you when your repo is published.

![remote repo URL](https://user-images.githubusercontent.com/44709545/159394141-9c981396-7fac-4803-9783-6618a30a6bf9.png)

Next, go back into Terminal/cmd and add our newly created GitHub repo as a remote that we can then push local repo changes by using this command: `$ git remote add origin https://github.com/yourusername/your-repo-name.git`

This command adds our GitHub repo as a remote where you can then push your local repo changes.

## Step 6: Push the Local Repo to GitHub

Next, we will need to push the local repo to GitHub by using this command: `git push origin master`

This line will upload the file or project on GitHub.

If you use -u in the command, it will remember you preferences for remote and branch. Then, you can simply use the command git push code line next time. The command is: `$ git push -u origin master`

## Step 7: Pull the Repo from GitHub

To pull the desired branch form the upstream repo, use this command: `$ git pull origin master`

This method will retain the commit history without modification.

# Branching, Stashing, and Merging in Git

## Git Stashing

The `git stash` command allows you to switch between branches whilst not forcing you to commit work you haven't finished so may return to it to finish later. Basically, stashing takes you modified tracked files and staged changes and saves it so that you can reapply them whenever you want.

### Viewing the Status of Your Work
Use `git status` to see if you have any changes that staged or not to be committed, which will result in a pop-up such as this:
````
$ git status
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   index.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   lib/README.md
````

### Stashing a File

To save the changes you have made on a file that you are currently working on, use this command: `$ git stash`

### List of Stashes

To view the list of stashes that you have made so far, use this command: `$ git stash list`

To stash a file with a message, use this command: `$ git stash save "stash message"`

It should look something like this: 

![stash list](https://mijingo.com/images/uploads/general/git-stash-list.png)

### Adding Commits to the file

To add a commit that takes the stash from the top of the stack, use this command: `$ git stash apply`

But, if you want to add a commit that uses a specific stash from the stack, use this command: `$ git stash apply stash@{#}` (where # is the stash number in the stack you that you want to use)

To add a commit and simultaneously delete it from the stash you have created, use this command: `$ git stash pop`

To do this with a specific stash, use this command: `$ git stash pop stash@{#}`

### Viewing the Stash Summary

To view the stash summary, use this command: `$ git stash show`

Or, if you want to view the full diff of a stash, use this command: `$ git stash show -p`

### Branching in Stash

To create a branch in your stash, use this command: `$ git stash branch <branch_name> stash@{#}`

### Clearing Stashes

To delete all of the stashes you have made, use this command: `$ git stash clear`

### Dropping stashes

To drop a specific stash that you have created, use this command: `$ git stash drop stash@{#}`

## Git Branching

Branching in Git is when a Branch is stored as a reference to a commit. Basically, it allows the user to create a copy of a specific commit without changing the original commit. This can be applicable for editing code that is not yours or to add comments for the original author to read. 

### Creating a Branch

To create a new branch, use this command: `$ git branch <branch_name>`

### List of Branches in Repo

To show the list of branches currently in your repo, use this command: `$ git branch` or `$ git branch --list`

### Navigating Between Branches

To switch between branches in your repo, use this command: `$ git checkout -b <branch_name>` 

### Deleting a Branch

To delete a specific branch, make sure the branch has been merged and then use this command: `$ git branch -d <branch_name>`

But if the branch has not been merged, use this command: `$ git branch -D <branch_name>`

## Git Merging

Merging in Git allows you to put a forked history back together again. The git merge command allows you to take separate lines of development created by a branch and integrate them into a single branch. The current branch will update to reflect the merge without affecting the target branch.

### Merging in a Local Repo

To merge onto a branch in a local repo, use these commands:
`$ git checkout main`, `$ git merge <branch_name>`

### Merging to a Remote Repo

To merge a branch to a remote repo, use this command: `$ git push --set-upstream origin <branch_name>`

### Updating a Branch

To update the main branch you have been working on if the original author has made changes, use these command: `$ git checkout <branch_name>`, `$ git merge main`# GitTutorial
