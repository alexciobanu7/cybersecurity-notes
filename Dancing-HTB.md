# Dancing - HTB starting point

## Objective 
- Enumerate SMG shares
- Connect to an accessible share
- Find the flag

## Key concepts
## SMB (Server Message Back)
- Network protocol used for file and printer sharing
- Common on Windows systems
- Ports:
  - 139 TCP NetBios Session Service
  - 445 TCP SMB

## SMB uses:
- File sharing
- Shared folders
- Network printers
- Active directory environments

## SMB shares 

A share is a folder exposed over the network.
Examples from this CTF challenge:

ADMIN$
C$
IPC$
Users
WorkShares

Some shares require credentials, while others may allow guest access. For example in this case, the WorkShares SMB share was poorly configured, allowing us to log in without the appropriate
credentials.

## Enumeration

> nmap -sV <target ip>

Expected to find:
- 139/tcp open netbios-ssn
- 445/tcp open microsoft-ds

This indicates SMB is running.

## Enumeratiog SMB shares

> smbclient -L <target ip>

-L   = List shares. Discovers available shares.

## Connecting to a share 

> smbclient \\\\<target ip>\\WorkShares

This opens an SMB session to the share.

## The other commands i used:

> ls

Typing ls i found two directories. One for Amy.J and one for James.P

In the James.P one i found the flag





