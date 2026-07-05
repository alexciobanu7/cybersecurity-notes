# Fawn HTB starting point

## Objective
- Discover an exposed FTP service
- Abuse anonymous FTP login
- Download the flag

## Key Concepts

## FTP (File Transfer Protocol)
- Used to transfer files between client and server
- Default port: 21/TCP
- Sends data and credentials in plaintext
- Common secure alternatives:
  - FTPS (FTP + SSL/TLS)
  - SFTP (FTP over SSH

## Anonymous login
- Common FTP misconfiguration
- Username: Anonymous
- Psw: Anything or blank
- Grants access without any real credentials

## Enumeration

## Connection checking

> ping <target ip>

The purpose of this command is to verity if the target connection is reachable.

## Scan for ports

> nmap -sV <target ip>

The '-sV' identifies the version of services 

## FTP access

> ftp <target ip>

Login:
- usr: anonymous
- psw: blank

## Other FTP commands

> ls
Listing files i found a txt file named flag.txt. So after that, i had to take the flag typing:
> less flag.txt


