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