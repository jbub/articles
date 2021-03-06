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

# use the test database
use test

# list all collections
show collections

# drop collection
db.items.drop()

# restore db from dump
mongorestore dump
```

## Querying

### Selecting: findOne(), find()

```
# select one item that satisfies the query specified
db.items.findOne()

# select all items that satisfies the query specified
db.items.find()

# show the results pretty printed
db.items.find().pretty()

# select all items with age equal to 20 and name equal to john
db.items.find({"age": 20, "name": "john"})
```

### Restricting selected fields

```
# select only age field
db.items.find({"age": 20, "name": "john"}, {"_id": false, "age": true})
```

### Comparison operators: $gt, $gte, $lt, $lte

```	
# select all items with score greater than 5
db.items.find({"score": {$gt: 5}})

# select all items with score greater to 5 and less than or equal to 20
db.items.find({"score": {$gt: 5, $lte: 20}})
```

### Checking if field exists: $exists

```	
# select all items with the score field present
db.items.find({"score": {$exists: true}})
```

### Checking if field is of a given type: $type

```	
# select items for which the score field is a type of a string
# http://docs.mongodb.org/manual/reference/glossary/#term-bson
db.items.find({"score": {$type: 2}})
```

### Using regular expressions: $regex

```	
# select all items matching the passed regular expression
db.items.find({"name": {$regex: "^a"}})
```

### Multiple queries: $or

```
# select all items with name equal to john or jack
db.items.find({$or: [{"name": "john"}, {"name": "jack"}]})
```

### Multiple queries: $and

```
# select all items with name equal to john and the age equal to 20
db.items.find({$and: [{"name": "john"}, {"age": 20}]})
```

### Querying inside arrays: $all, $in

```
# in a document like this {"name": "jonn", "categories": ["car", "plane"]}
# this would find all items with the car category
db.items.find({"categories": "car"})

# this would find all items with the car and plane categories
db.items.find({"categories": {$all: ["car", "plane"]}})

# this would find all items with the car or plane categories
db.items.find({"categories": {$in: ["car", "plane"]}})
```	

### Using dot notation for querying inside nested documents

```
# in a document like this 
# {"name": "john", "categories": [{"name": "test", {"name": "car"}}]}
# this would find all items with the nested category name car
db.items.find({"categories.name": "car"})
```

### Sorting, skipping and limiting results: sort(), skip(), limit()

```
# select all items sorted by the score field in the descending order
# skip first 50 items and limit the result to 20 items
db.items.find().sort({"score": -1}).skip(50).limit(20)
```

### Counting results: count()

```
# count all items with the type equal to car
db.items.count({"type": "car"})
```

### Updating results: update(), $set, $unset, $inc

```
# update all items with the type equal to car to and set the score to 50
# note that this replaces the whole document with the new one {"score": 50}
db.items.update({"type": "car"}, {"score": 50})

# set the score to 50, create the score field if not present
# note that this will keep the original structure of the document
db.items.update({"type": "car"}, {$set: {"score": 50}})

# increment the score by 1, set the score field to 1 if not present
# note that this will keep the original structure of the document
db.items.update({"type": "car"}, {$inc: {"score": 1}})

# remove the score field from all the documents matching the query
db.items.update({"type": "car"}, {$unset: {"score": 1}})
```

### Inserting

```
# insert new item to database
db.items.insert({"name": "john"})
```		


