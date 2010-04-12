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
* **INCR** - increment the integer value of key (atomically) 
* **DECR** - decrement the integer value of key (atomically)
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

* **SADD**/**SREM** - add/remove the specified member to the set value at key
* **SISMEMBER** - test if the specified value is a member of the set at key
* **SINTER** - intersection between the sets stored at key1, key2, ...keyN
* **SUNION** - return the union between the sets stored
* **SDIFF** - return the difference between the sets
* **SRANDMEMBER** - a random member of the set value at key
## ... :iceberg => "tip"

!SLIDE small

# For a full command reference see 
## http://code.google.com/p/redis/wiki/CommandReference

!SLIDE incremental bullets

# So what's cool about this?
* It's very fast.
* It often closely models our beloved Ruby classes; think Array#pop, shift, +, etc.
* May require less cognitive overhead for some tasks.

!SLIDE

# Not quite there yet
TODO

!SLIDE bullets

# Running Redis

* Linux, BSD, Mac OS X, Solaris
* No official support for Windows
* Root privs not needed to get started

!SLIDE center

## http://code.google.com/p/redis/
### Also on github: http://github.com/antirez/redis

![Redis at Google](google-redis.png)

!SLIDE incremental bullets transition=scrollLeft smbullets

# How fast is Redis?
###*or, why people like Redis

* Tested with redis-benchmark
* 50 simultaneous clients, 100000 requests, using loopback
* SET and GET with 256 bytes string
* Linux 2.6 on a Xeon X3320 2.5Ghz
* About 110,000 SETs per second, and 81,000 GETs per second

!SLIDE incremental bullets

# Other points of interest

* Supports master/slave replication
* Written in ANSI C, easy to compile and install
* Past work sponsored by Engine Yard & Citrusbyte
* Currently sponsored by VMWare

!SLIDE bullets incremental

# Who is using Redis?

* Engine Yard
* Craigslist
* Guardian.uk
* Ruby Minds
* Github
* You?
