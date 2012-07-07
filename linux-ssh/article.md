# SSH

## Logging without password

The common problem with ssh is to enter your password every time you log in. To automatize this, you can generate a pair of keys and copy the public one to the remote server. This way you can log in without typing password every time.

### Generate keys on your local machine

Generate a new pair of keys and save it under /home/user/.ssh/id_rsa. Do not enter any passphrase if you do not want to type it every time you log in.

	# generate keys with name rsa
	ssh-keygen -t rsa
	
	# so now we have two keys
	/home/user/.ssh/id_rsa # private
	/home/user/.ssh/id_rsa.pub # public
	
### Make sure the .ssh folder exists on the remote server

You can create it easily by this command:

	ssh user@remote mkdir -p .ssh
	
### Add the public key to the remote server

In order to be recognized by the remote server we must append the contents of our public key into the .ssh/authorized_keys file.

	cat .ssh/id_rsa.pub | ssh user@remote 'cat >> .ssh/authorized_keys'
	
	