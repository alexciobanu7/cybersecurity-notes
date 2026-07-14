## Appointment - HTB Starting Point

# Target
- Identify a web application running on the target
- Discover a vulnerable login form
- Exploit SQL injection (SQLi)
- Bypass authentication and capture the flag

# Key concept
# Web Application Enumeration
When Nmap reveals a web service:

> 80/tcp
> 443/tcp

Your next step is usually:
- Open the website in a browser
- Inspect pages and forms
- Look for input fields
- Test for vulnerabilities

Common web attack surfaces:
- Login forms
- Search boxes
- URL parameters
- Cookies
- File uploads

# SQL Injection
# What is SQL Injection?
SQL injection (SQLi) is a cyberattack where hackers insert malicious code into a website's input fields (like a login box) to trick the underlying database into exposing or destroying hidden data.

Example of a vulnerable SQL code:

> SELECT * FROM users 
> WHERE username='$username' 
> AND password='$password';

So if an attacker enters in the login form:
> admin'#

The query becomes:
> SELECT * FROM users
> WHERE username='admin' #'
> AND password='';

'#' comments out the rest of the SQL query, and the password check is ignored.

# Common SQL Injection Characters:

- '
- "
- ;
- '--'
- '#'















