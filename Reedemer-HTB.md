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















