# SQL Injection Notes

## What is SQL Injection?

SQL Injection is a web vulnerability that allows an attacker to manipulate database queries by inserting malicious input into application fields.

It happens when user input is not properly validated or sanitized.

Example vulnerable query:

SELECT * FROM users WHERE username = 'admin' AND password = '1234';

If the application does not filter input, the attacker can change the query logic.

---

## How SQL Injection works

User input is directly added to the SQL query.

Example input:

admin' OR 1=1 --

Query becomes:

SELECT * FROM users WHERE username='admin' OR 1=1 -- ' AND password='test';

1=1 is always TRUE → login bypass possible.

---

## Types of SQL Injection

### 1. Error-Based SQL Injection
The database shows an error message.

Example:
'
"

Helps the attacker understand the database structure.

---

### 2. Union-Based SQL Injection
Attacker extracts data using the UNION keyword.

Example:
' UNION SELECT null, null --

---

### 3. Blind SQL Injection
The application does not show an error, but the response changes.

Example:
1 AND 1=1
1 AND 1=2

---

## Common SQL Injection payloads

' OR '1'='1
admin' OR 1=1 --
' OR 1=1#
' UNION SELECT null, null --
1' ORDER BY 1 --
1' ORDER BY 2 --
' AND 1=1 --
' AND 1=2 --

---

## Impact of SQL Injection

• Login bypass
• Extract database data
• Dump usernames & passwords
• Modify database
• Delete data
• Gain admin access

---

## Prevention methods

• Use prepared statements
• Input validation
• Parameterized queries
• ORM frameworks
• Least privilege database access

Example secure query:

SELECT * FROM users WHERE username =? AND password =?

---

## Tools used for SQL Injection testing

• Burp Suite
• sqlmap
• browser developer tools

---

## Status

Concept understood.
