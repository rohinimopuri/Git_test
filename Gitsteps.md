# Git steps to clone, branch, and push new changes.

## Part 1: Clonning a Repository

Follow the steps inorder to clone a Repository into your local space.

```git
$ git clone <https link to the repo> 
              (OR) 
$ git clone <https link to the repo> <optional user specified directory name to clone the repo into>

```
- If there is no directory name specified it will the use the name of the repo to create a directory. 
- You only need to clone the repo once onto your local. 
- All the updates can be made from the cloned repo on local. 


## Part 2: Checking the Status of the Repository on CMD. 
```
$ cd <repository directory in local>
```
- To check the status of the repository use the command below. This command will give all the information about the repo, the branch it is on, if the branch is clean, if the branch has any uncommited files etc. 

```git
$ git status
```
- Make sure the branch is always clean without any uncommited files. 
- To make sure you have the latest information, do a pull of the remote repository.

```git
$ git pull origin <branch you are on> 
	      (OR) 
$ git pull
```

## Part 3: Creating Branches

- Check if a develop branch is present for the repo. The command below should show all the branches present. 
- The current branch it is on is usually shown with an “*”
```git
$ git branch
```
- If a develop branch is not present, create a develop branch. In this case '[name_of_your_new_branch]' = "develop".
```git
$ git checkout -b [name_of_your_new_branch]
```

## Part 4: Checking onto a branch

- To checkout a branch you want to work on, use the following command.

```git
$ git checkout [name_of_your_new_branch]
```
- Always check the status of your branch after checking out to make sure it is upto date and no uncommited files.

## Part 5: GIT flow to follow

- After Cloning the required Repo, creating a develop branch and checking if the branches are clean, follow the steps below.

- Checkout a feature branch from the develop branch to make any changes. 

```git
$ git checkout -b feature/<give a meaningful name for the changes. Use a date and title> 
```
- Once the changes are made, you can do a “git status” to see what files have been changes and what needs to be added to the repo. 

## Part 6:  Adding and Commiting files

- Add files: this step stages the files for adding to the repo 
```git
$ git add <names of the files separated by a space> 
                     (OR)
$ git add . 
(this will add the files irrespective of changes made)
```

## Part 7: Commiting the changes

- Commit the files: This step adds the files to the repo and will be recorded. Each commit has a string of characters associated with it (commit ID). 
```git
$ git commit -m “meaningful message for the commit”
```
- Use the log to see the history of all the commits along with the commit ID's 
```git
$ git log 
```
## Part 8: Push the changes

-After completing the commit, we need to push the changes to the remote repository. 

```git
$ git push origin <name of the branch you are making the changes on> 
```

## Part 9: Pull request

- The following are the steps on how to send a pull request from the GitHub page
	- Go onto the GitHub page on the web.
	- On the repo main page, you should be able to see an option for create pull request. 
	- Select the two branches you want to merge. Develop and the feature branch where the changes were made and pushed.
	- Create pull request and assign a person to review it.
	- Once approved, merge the changes onto develop.

- Once the changes have been merged on the GitHub page, back on the command line
	- checkout the develop branch
	```git
	$ git checkout develop
	```
	- Pull the merge changes
	```git
	$ git pull origin develop
	```
	- Merge to master
	```git
	$ git checkout master
	$ git merge develop
	```	
## Part 10: Tag the change

- After merging all the changes to the master, tag the change accordingly. 
- Tags must be used only on the master branch. 

```git
$ git tag <version of the changes, Ex: v1.1.0 >
$ git push --tags
$ git push origin master (Push all the changes to remote)
```

- Checkout the tag to use.
```git
$ git checkout v1.0.0
```

## Versioning : How to use versions in tag

- For major changes in scripts or releases use the Major version increment.
	- Ex: v1.0.0 --> v2.0.0
- For smaller bug fixes or small changes use the Minor version increment.
	- Ex: v1.0.0 --> v1.1.0
- For simple changes we can use the Micro version increment.
	- Ex: v1.0.0 --> v1.0.1





