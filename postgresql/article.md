# PostgreSQL

Some commands for running your own local PostgreSQL server.

## Installing using macports

	sudo port install postgresql84
	sudo port install postgresql84-server
	
## Creating default database instance

In order to run server, we need to initialize the database with the data directory. Note that this directory must be owned by the postgres user.

	sudo mkdir -p /path/to/db
	sudo chown postgres:postgres /path/to/db
	sudo su postgres -c '/opt/local/lib/postgresql84/bin/initdb -D /path/to/db'
	
## Change the shell for the postgres user to bash

I prefer bash as a default shell, so lets just change it for the postgres user too.

	sudo dscl . -create /Users/postgres UserShell /bin/bash
	
## Verifying postgres user and group

Generally it is a good idea to check on the postgres user and group.

	dscl . -read /Users/postgres
	dscl . -read /Groups/postgres
	
## User permissions

Note that after installing PostgreSQL, all local users can connect to the database server. In order to set the permissions you must edit the "pg_hba.conf" located in your data directory. When trust authentication is specified, PostgreSQL assumes that anyone who can connect to the server is authorized to access the database with whatever database user name they specify.

	# "local" is for Unix domain socket connections only
	local   all         all                               trust
	# IPv4 local connections:
	host    all         all         127.0.0.1/32          trust
	# IPv6 local connections:
	host    all         all         ::1/128               trust
	
## Path

It is a good step to add the bin directory of PostgreSQL install to your path. Now you can use the pg_ctl control script directly.

	export PATH='/opt/local/lib/postgresql84/bin':$PATH
	
## Starting and stopping the server

Now we can finally run our server with specifying the data directory and the log path. 

	pg_ctl -D /path/to/db -l /path/to/log/postgres.log start
	

To stop the server you can use the similar syntax:
	
	pg_ctl -D /path/to/db -l /path/to/log/postgres.log stop
