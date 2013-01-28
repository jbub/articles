# MongoDB

Some notes from learning about MongoDB and the Python driver.

```
# create mongo data folder and make it writable
mkdir /data/db
chmod 777 /data/db

# run mongo server
mongod

# run mongo shell
mongo
```
	
Inside mongo shell.

```
# show actual database
db

# list all databases
show dbs

# select database test
use test

# list all collections
show collections
	
# pointing to a collection
db.test	

# drop collection
db.test.drop()

# restore db from dump
mongorestore dump

# find one document that satisfies the query specified
db.test.findOne()

# find all documents that satisfies the query specified
db.test.find()

# insert new document to database
db.test.insert({"name": "john"})
```		

