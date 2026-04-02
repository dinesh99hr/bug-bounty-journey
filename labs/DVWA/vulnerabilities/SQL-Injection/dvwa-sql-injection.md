# SQL Injection - DVWA Lab

## Objective
Learn how SQL Injection works and how an attacker bypasses login forms.

## Lab Setup
Application: DVWA 
Security Level: Low / Medium
URL: http://192.168.1.86/DVWA/vulnerabilities/sqli/

## What is SQL Injection?
SQL Injection happens when user input is inserted into a database query without proper validation.

An attacker can manipulate the query to bypass login or extract data.

## Example payloads Tested

1. Basic test
' OR '1'='1

2. login bypass 
admin' OR 1=1 --

3. Error-based test
' OR 1=1#

## Steps performed

1. Open DVWA
2. Go to the SQL Injection page
3. Intercept request to Repeater
4. Send request to Repeater
5. Modify parameter value
6. Observe response

Example request:

id=1' OR '1'='1

## Result

Application returned multiple user records.

Login bypass is possible.

## Learning 

Input validation is important.
Parameterized queries prevent SQL Injection.

SQL Injection types:
- Error-based
- Union-based
- Blind SQL Injection

## Status
SQL Injection lab successfully tested.




