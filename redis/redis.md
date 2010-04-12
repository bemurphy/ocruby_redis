!SLIDE subsection

# What is Redis?

!SLIDE center transition=scrollUp

![Holy Cow, Radishes!](radish.jpg)

# No, not that!

!SLIDE incremental bullets

# Redis Is...

* An advanced key-value store
* Similar to memcached but the dataset is non-volatile...
* ...distinct from memcached in that it supports advanced data beyond strings

!SLIDE incremental bullets

## What kind of datatypes does it support?

* Strings
* Lists
* Sets
* Sorted sets

!SLIDE incremental bullets smbullets

# Operating on Strings

* **SET** - set a key to a string value
* **GET** - return the string value of the key
* **GETSET** - set a key to a string returning the old value
* **MGET** - multi-get, return the values of multiple keys
* **SETNX** - set a key to a string value if the key does not exist
* **INCR** - increment the integer value of key, atomically
* **DECR** - decrement the integer value of key, atomically
## ...and more!

!SLIDE incremental bullets smbullets

# Operating on Lists

* **LPUSH**/**RPUSH** - append an element to the head or tail of the list
* **LLEN** - return the length of the list
* **LRANGE** - return a range of elements
* **LTRIM** - trim the list to the specified range of elements
* **LPOP**/**RPOP** - return and remove (atomically) the first or last element
## ...and *way* more!

!SLIDE incremental bullets smbullets

# Operating on Sets

* SADD key member Add the specified member to the Set value at key
* SREM key member Remove the specified member from the Set value at key
* SPOP key Remove and return (pop) a random element from the Set value at key
* SMOVE srckey dstkey member Move the specified member from one Set to another atomically
* SCARD key Return the number of elements (the cardinality) of the Set at key
* SISMEMBER key member Test if the specified value is a member of the Set at key
* SINTER key1 key2 ... keyN Return the intersection between the Sets stored at key1, key2, ..., keyN
* SINTERSTORE dstkey key1 key2 ... keyN Compute the intersection between the Sets stored at key1, key2, ..., keyN, and store the resulting Set at dstkey
* SUNION key1 key2 ... keyN Return the union between the Sets stored at key1, key2, ..., keyN
* SUNIONSTORE dstkey key1 key2 ... keyN Compute the union between the Sets stored at key1, key2, ..., keyN, and store the resulting Set at dstkey
* SDIFF key1 key2 ... keyN Return the difference between the Set stored at key1 and all the Sets key2, ..., keyN
* SDIFFSTORE dstkey key1 key2 ... keyN Compute the difference between the Set key1 and all the Sets key2, ..., keyN, and store the resulting Set at dstkey
* SMEMBERS key Return all the members of the Set value at key
* SRANDMEMBER key Return a random member of the Set value at key

!SLIDE small

# For a full command reference see 
## http://code.google.com/p/redis/wiki/CommandReference

!SLIDE incremental bullets

# So what's cool about this?
* It's fast.
* May require less cognitive overhead for some tasks.
* It more closes models our beloved Ruby classes, like Array#pop, slice, shift, etc.

!SLIDE center

## http://code.google.com/p/redis/
### Also on github: http://github.com/antirez/redis

![Redis at Google](google-redis.png)

!SLIDE incremental bullets

# Other points of interest

* Supports master/slave replication
* Written in ANSI C, easy to compile and install
* Past work sponsored by Engine Yard & Citrusbyte
* Currently sponsored by VMWare

!SLIDE incremental bullets transition=scrollLeft smbullets

# How fast is Redis?
###*or, why people like Redis

* Tested with redis-benchmark
* 50 simultaneous clients, 100000 requests, using loopback
* SET and GET with 256 bytes string
* Linux 2.6 on a Xeon X3320 2.5Ghz
* About 110,000 SETs per second, and 81,000 GETs per second