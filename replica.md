# what is replica set
copy data to other servers  
primary server -> secondary server sync  

# minimum design
- primary  
- secondary  
- arbiter  
each server has vote, watch each other by ping  
total server must be odd to determine primary  

only primary is written, but we can distrubute burden to primary and secondary , because secondary has the same data  

## settable value to model
primary  
primaryPreffered  
secondary  
secondaryPreffered  
nearest  

## concern read
read only data which exist primary and secondary  

## settable value to read concern
local  
majority  
linerizable  


# how to sync each other
1. create replica set => automatically created oplog collection
2. app writes data to test collection in primary server
3. primary writes data to oplog
4. secondary go to see primary oplog asyncly and check diff. If diff, write diff to secondary oplog  
5. reflect data to test collection by secondary oplog




