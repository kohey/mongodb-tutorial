# index
algorism = B-Tree  

# create Index
`db.collection.createIndex({key: 1 or -1, ...,} {option})`  
option:  

background  
name  
unique  
partialFilterExpression  

use background if already many docs  

# index kind(main)
defaultIndex  
textIndex  
TTLIndex  

# where should add index
1. to shard key  
2. frequently use to serch  
3. used to connect collections

# optimize query
1. find slow query  
2. test slow query  

## find slow query
set profiler  

# setting
## journal
func to temporary save data  
this is important because mongo writes data to disk every 60sec  
if system down while this 60 sec, the data gone  


## storage engine
WiredTiger is the best  



