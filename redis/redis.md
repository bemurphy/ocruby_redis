!SLIDE subsection

# What is Redis?

!SLIDE center

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

!SLIDE incremental bullets

# Other interesting basics

* Supports master/slave replication
* Written in ANSI C, easy to compile and install
* Past work sponsored by Engine Yard & Citrusbyte
* Currently sponsored by VMWare

!SLIDE incremental bullets

# How fast is Redis?

* Tested with redis-benchmark
* 50 simultaneous clients, 100000 requests, using loopback
* SET and GET with 256 bytes string
* Linux 2.6 on a it's Xeon X3320 2.5Ghz
* About 110000 SETs per second, about 81000 GETs per second