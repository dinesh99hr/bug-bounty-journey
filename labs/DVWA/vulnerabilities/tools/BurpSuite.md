# Day 2 - Burp-Suite Intercept & Repeater

## Objective
Understand how to intercept HTTP requests and modify parameters using Burp Suite.

## Tool Used
Burp-Suite Community Edition

## Lab
DVWA Login Page

URL: http://192.168.1.86/DVWA/login.php

## Steps Performed

1. Started Burp Suite
2. Turned Intercept = ON
3. Configured Firefox proxy (127.0.0.1) (port:8080)
4. Opened DVWA login page
5. Entered test credentials
6. Capture POST request

Example request: POST /DVWA/login.php HTTP/1.1

Username=test&password=test123&Login=Login

7. Sent request to Repeater
8. Modified parameters:

username=admin
password=test123

9. Observed server response

HTTP/1.1 302 Found
Location: index.php

##Learning

GET request -> loads page

POST request -> sends data to server

Burp allows modifying of request parameters before they reach the server.

Useful for testing:
- SQL Injection
- XSS
- Authentication bypass
- IDOR

## Result

Successfully intercepted and modified the login request.

Day 2 completed
