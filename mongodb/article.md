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


## Basic commands

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
db.items

# drop collection
db.items.drop()

# restore db from dump
mongorestore dump
```

## Querying

```
# find one item that satisfies the query specified
db.items.findOne()

# find all items that satisfies the query specified
db.items.find()

# show the results pretty printed
db.items.find().pretty()

# find all items with age equal to 20 and name equal to john
db.items.find({"age": 20, "name": "john"})

# select only age field
db.items.find({"age": 20, "name": "john"}, {"_id": false, "age": true})

# select all items with score greater than 5
db.items.find({"score": {$gt: 5}})

# select all items with score greater to 5 and less than or equal to 20
db.items.find({"score": {$gt: 5, $lte: 20}})

# select all items with the score field present
db.items.find({"score": {$exists: true}})

# look for items which the score field is a type of string
# http://docs.mongodb.org/manual/reference/glossary/#term-bson
db.items.find({"score": {$type: 2}})

# select all items matching the passed regular expression
db.items.find({"name": {$regex: "^a"}})

# select all items with name equal to john or the age equal to 20
db.items.find({$or: [{"name": "john"}, {"age": 20}]})

# insert new item to database
db.items.insert({"name": "john"})
```		

