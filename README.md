#load2redis

##What is it?

load mysql data to redis by sql query


##build for every platform
```
gox 
```

## to hash
```

./load2redis -u test -p test -s localhost:3306 -d test -q "SELECT concat( 'user:', c.id ) Rkey, c.name name c.mark mark FROM user c WHERE c.id  > 0;" -rs localhost:6379 -rp [redis password] -ds hash -size 1200

```

## to set

```
./load2redis -u test -p test -s localhost:3306 -d test -q "SELECT concat( 'group:', c.id ) Rkey, c.id id FROM group c WHERE c.id  > 0;" -rs localhost:6379 -rp [redis password] -ds set -size 1200

```

## to k/v

```
./load2redis -u test -p test -s localhost:3306 -d test -q "SELECT concat( 'group:', c.id ) Rkey, c.id id FROM group c WHERE c.id  > 0;" -rs localhost:6379 -rp [redis password] -ds key -size 1200

```