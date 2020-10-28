# Git steps to clone, branch, and push new changes.

## Part 1: Clonning a Repository

Follow the steps inorder to clone a Repository into your local space.

```git
git clone <https link to the repo> OR git clone <https link to the repo> <optional user specified directory name to clone the repo into>

```
- If there is no directory name specified it will the use the name of the repo to create a directory. 

## Part 2: Checking the Status of the Repository on CMD. 
```
cd <repository directory in local>
```
- To check the status of the repository use the command below. This command will give all the information about the repo, the branch it is on, if the branch is clean, if the branch has any uncommited files etc. 

```git
git status
```
- Make sure the branch is always clean without any uncommited files. 
- To make sure you have the latest information, do a pull of the remote repository.

```git
git pull origin <branch you are on> 
			(OR) 
git pull
```

## Part 3: Creating Branches



4.	Check if a develop branch is not present for the repo, create a develop branch. 
a.	git branch 
i.	should show all the branches present. The current branch it is on is usually shown with an “*”
ii.	check out onto the develop branch.
1.	git checkout develop
iii.	You can also do a git status to see what branch you are currently on
b.	If no develop branch is present create a develop branch.
i.	git checkout -b develop
c.	git status to see if you on the develop branch.
5.	Once on the develop branch make sure it is up to date.
a.	git pull origin develop
6.	Checkout a feature branch to make changes.
a.	git checkout -b feature/<give a meaningful name for the changes. Use a date and title> 
7.	Once the changes are made, you can do a “git status” to see what files have been changes and what needs to be added to the repo. 
8.	add the files ,this step stages the files for adding to the repo 
a.	git add <names of the files separated by a space> (OR)
b.	git add . (this will add the files irrespective of changes made)
9.	Commit the files. This step adds the files to the repo and will be recorded. Each commit has a string of characters associated with it (commit ID). 
a.	“git log” will give a history of all the commits with the commit ID. 
b.	git commit -m “meaningful message for the commit”
10.	Push all the changes
a.	git push origin <name of the branch you are making the changes on> 
11.	Sending a pull request
a.	Go onto the GitHub page on the web.
b.	On the repo main page, you should be able to see an option for create pull request. 
c.	Select the two branches you want to merge. Develop and the feature branch
d.	Create pull request and assign a person to review it.
e.	Once approved, merge the changes onto develop.
12.	Back on the command line,
a.	git checkout develop
b.	git pull origin develop
13.	Merge to master
a.	git checkout master
b.	git merge develop
c.	git tag v1.0.0
d.	git push --tags
e.	git push origin master
14.	Checkout the tag
a.	git checkout v1.0.0


Appendix:
A.	how to use versions in tag

For major changes in scripts or releases use the Major version increment.
Ex: v1.0.0 --> v2.0.0
For smaller bug fixes or small changes use the Minor version increment.
Ex: v1.0.0  v1.1.0
For simple changes (to be defined) we can use the Micro version increment.
Ex: v1.0.0  v1.0.1





