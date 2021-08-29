# sharding 
separate data to other machine  
This needs two server, mongos / config  

App -> mongos -> config -> mongos -> DB server -> mongos -> App  

## chunk
collect data as chunk, and if flows, relay to next server.  
Its important to choose shard key

## which to choose as shard key
not to choose
- not use to search
- simply increase or descreese key
- cardinarity low key

it's important to set several keys for sharding.  

ex. 
if board, userId and posted date.  
