!SLIDE subsection transition=cover

# Getting Ruby on Redis

!SLIDE center

![On github, of course.](redis-rb.png)

## It's on github, of course!

!SLIDE commandline incremental

## Quick Start

    $ sudo gem install ezmobius-redis-rb
    
    $ /path/to/redis-server
    11 Apr 21:10:31 - Server started, Redis version 1.2.6
    11 Apr 21:10:32 - DB loaded from disk
    11 Apr 21:10:32 - The server is now ready to accept connections on port 6379
    11 Apr 21:10:32 . DB 0: 75535 keys (0 volatile) in 131072 slots HT.
    11 Apr 21:10:32 . 0 clients connected (0 slaves), 24243472 bytes in use, 0 shared objects

    $ irb
    >> require "redis"
    => true
    >> redis = Redis.new
    => #<Redis:0x113d4e4 @host="127.0.0.1", @timeout=5, @sock=#<TCPSocket:0x113d46c>, db0, port6379
    >> redis.set("foo", "bar")
    => true
    >> redis.get("foo")
    => "bar"
        
!SLIDE transition=fade

# More Ruby Usage
    
!SLIDE code transition=blindX

    @@@RUBY
	  
    require 'redis'
    r = Redis.new
    r['key_one'] = "value_one"
    r['key_two'] = "value_two"

    r['key_one]  # => "value_one"
    
    # Note: values are typed, but all keys 
    # are strings
    
!SLIDE code transition=zoom

    @@@RUBY

    require 'redis'

    # Connect to local server
    r = Redis.new

    # Make sure it's zeroed
    r.delete 'counter'

    # Count up...
    r.incr('counter') # => 1
    r.incr('counter') # => 2
    r.incr('counter') # => 3

    # And count down...
    r.decr('counter') # => 2
    r.decr('counter') # => 1
    r.decr('counter') # => 0
	
!SLIDE smaller code transition=zoom

    @@@RUBY

    require 'redis'

    r = Redis.new

    r.delete 'foo-tags'
    r.delete 'bar-tags'

    # create a set of tags on foo-tags
    r.set_add 'foo-tags', 'one'
    r.set_add 'foo-tags', 'two'
    r.set_add 'foo-tags', 'three'

    # create a set of tags on bar-tags
    r.set_add 'bar-tags', 'three'
    r.set_add 'bar-tags', 'four'
    r.set_add 'bar-tags', 'five'
    r.set_add 'bar-tags', 'five' # Not a typo, it's a set!

    r.set_members('foo-tags') # => ["three", "two", "one"]

    r.set_members('bar-tags') # => ["four", "three", "five"]

    # Unions & Intersections
    r.set_union('foo-tags', 'bar-tags') 
      # => ["four", "three", "five", "two", "one"]
    r.set_intersect('foo-tags', 'bar-tags') # => ["three"]
    
