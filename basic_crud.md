# create Databse 
1. `use testdb`
2. `db.createCollection("hogehoge")`
=> at this point, the db is actually created.

# crud colleciton  
- create collection  
`db.createCollection("hogehoge")`  
- drop  
`db.hogehoge.drop()`  
- insert  
`db.collection.insertOne({ key: value})`  
you can also use `insertMany`  
- find
`db.collection.find()` => returns all  
`db.hogehoge.find({}, {_id:0, name: 1})` => show only name field from hogehoge collection
`db.hogehoge.find{_id:0, "child.name": 1}` => show only name `in` child field  
`db.collection.find({key: /value/})` => partial match  
`db.collection.find({key: /^value/})` => forward match  
`db.collection.find({key: /value$/})` => backforward match  
```
db.collection.find({
    $and: [
        {key: value},
        {key: value}
    ]
})
```  
`db.collection.find().sort({ key1: 1, key2: -1})` => sort  

- update  
almost same as find  
`db.hogehoge.updateOne({query}, {$set: {updateContent}})`  
`replaceOne`  

- aggregate  
you can use aggregate by grouping data


# tips
- capped collection  
collection which limits the capacity of collection.  
This is used for logging, because this removes old versions if limit exceeded.  

If you want to convert normal collection to capped,  
`db.runCommand({"convertToCapped": collectionNeme, size: sizeLimit})`  

    - you cannot change limit after  
    - you cannot delete nor update data  
    - you cannot shardding  
