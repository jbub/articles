## Adding users

Adding users on unix based systems is fairly easy. First you have to become root or you can use the sudo command. Usually there are two ways. You can use the **adduser** perl script which will ask you for all important data. The second way is to use the **useradd** command. The perl script is actually a nice wrapper around the useradd command.

### useradd usage

This example will just create a new user called john. Note that you have to create the home directory by yourself. Also you need to specify a password with the **passwd** command. Do not forget to **chown** the home directory for the user.
	
	# create user
	useradd john        
	# add user password         
	passwd john                 
	# create home directory 
	mkdir /home/john        
	# set john as owner of his home directory
	chown john:users /home/john  

### useradd options

Creating user with home directory. The /home/username path will be used by default.

	useradd -m john

Creating user with some info.

	useradd -c "John User" john

Creating user with the home directory.

	useradd -d /home/john john

Creating user and adding him to primary and other groups.

	useradd -g primarygroup -G group1 group2 john

Creating user with the default shell.

	useradd -s /bin/bash john
	
Creating user with the encrypted password, as returned by crypt. User will be disabled if no password is set.

	useradd -p password john

Creating user with the date on which the user will be disabled. Date format is YYYY-MM-DD.

	useradd -e 2012-11-21 john

Creating user with the number of days after a password expires until the account is permanently disabled.

	useradd -f 20 john

Please refer to the useradd man page for more options and informations.


