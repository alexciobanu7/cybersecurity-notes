# Redeemer – HTB Starting Point

## Target
- Discover a Redis service.
- Connect to the Redis database
- Enumerate stored keys
- Capture the flag

## Key concepts
## Redis (Remote Dictionary Server) in an in-memory NoSql database commonly used for:
- Caching
- Session storage
- Message queues
- Fast key value storage

## Default port
> 6379/TCP

## Redis stores data as:
> KEY --> VALUE

## Why Redis is dangerous when exposed 
## Many Redis servers are:
- Exposed to the internet
- Unauthenticated
- Misconfigured

## If authentication is disabled, anyone can:
- Read stored data
- Modify data
- Potentially gain code execution (in some scenarios)

## Enumeration

## Scanning the target

> nmap -p- -sV 'target ip'

-p-: the -p- flag is a shortcut option used to scan all 65,535 possible network ports, as the server was running on a non-standard port outside of nmap's default list

## Expected resut
> 6379/tcp open redis

## Connecting to Redis
Before connecting to Redis I wanted to inform myself more about it and view its help page by typing:
> redis-cli --help

After that, I needed to use the following switch for specifying the host that I need to connect to:
> redis-cli -h 'target ip'

-h = hostname

Upon the successful connection with the Redis server, i had to use the info command, which returns information and statistics about the Redis server:
> 10.10.10.127:6379 info

There was keyspace section, which provides statistics on the main dictionary of each database. The statistics include the number of keys, and the number of keys with an expiration.

Example:
> Keyspace
> db0:key=4, expires=0, avg_ttl=0

In my case, under the Keyspace section, I can see that only one database exists with index 0. So I used the select command followed by the index number of the database that needs to be selected:
>select 0

And it should come up with a message "OK"
After that I listed all the keys present in the database using the command:
> keys *

Example of the outcome:

temp
users
flag
session

















