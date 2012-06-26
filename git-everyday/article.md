# Git everyday 


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
	
### Listing repos

	git remote    # just aliases
	git remote -v # aliases with urls
	
