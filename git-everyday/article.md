# Git everyday 

## Adding

Git has a staging area which is area between your working copy and repository. You can add files to the index using git add command. Git adds files with respect to the .gitignore file.

	git add .  # adds all files
	git add -u # adds deleted files
	git add -A # shortcut for both previous steps
	
------

## Aliases

Git allows us to create shortcuts for frequently used commands in form of aliases. 

### Adding aliases

	git config --global alias.pl "pull origin master"
	git config --global alias.ps "push -u origin master"
	git config --global alias.st "status" 
	git config --global alias.sb "submodule"
	
### Deleting aliases

	git config --global --unset alias.name
	
### Listing aliases

	git config --global --get-regexp alias

------

## Branches

A branch in Git is a pointer to a specific commit. The default branch name in Git is master.

### Adding branches

	git branch branch_name
	
This creates a new branch at the same commit as is your current branch.
	
### Switching to a branch

	git checkout branch_name

### Renaming branches

	git branch -m old_branch new_branch

### Pushing new local branch to remote

	git push origin branch_name
	
### Pulling new remote branch 

	git checkout -b branch_name origin/branch_name
	
### Deleting branches

	git branch -d branch_name
	
### Merging new branch into master

	git checkout master
	git merge new_branch
	
### Listing branches

	git branch    # local
	git branch -r # remote
	git branch -a # local and remote
	
------
	
## Remotes

Gits lets you define a number of remote repositories to work with.


### Adding remotes

	git remote add alias_name user@host.com:repo_name.git
	
### Deleting remotes

	git remote rm alias_name
	
### Listing remotes

	git remote    # just aliases
	git remote -v # aliases with urls
	
------
	
## Submodules

### Adding submodules

	git submodule add user@host.com:repo.git path/to/submodule
	
### Initing and updating submodules
	
	# from the project root
	git submodule init
	git submodule update
	
### Deleting submodules

First you need to delete submodule from the **.gitmodules** file located in your project root. Then delete submodule from your git **config** file located in **.git** folder of your project root. Then you need to run following command (note that there is no trailing slash):

	git rm --cached path/to/submodule 
	
After that you just need to commit changes and delete the untracked submodule data.

### Editing submodule contents from your project

You can directly edit contents of your submodules from your project. After updating your submodules using submodule update command, your submodules are checked out, but not within a branch. So before making any changes, you need to be sure that your submodule is on specific branch. Now you can make the changes and then from the subproject root commit them.

------
	
## Reverting changes

### Commited but not pushed to remote

If you want to remove last commit but leave the files staged just use the --soft option for the git reset command. On the other hand, if you want to get rid of the changes to tracked files in the working tree use --hard option for that.

	# HEAD~1 is shorthand to the first commit before HEAD
	git reset --soft HEAD~1
	
### Commited and pushed to remote

You cannot use git reset for this scenario, you want to use the git revert instead.
	
	# this will create a new commit reverting all changes by the last one
	git revert HEAD

------

## Merging

### Dry run

	# it will not allow fast forward neither it will commit any changes
	# it will leave updated files in your staging area
	git merge --no-ff --no-commit master
