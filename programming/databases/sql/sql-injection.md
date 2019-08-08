# SQL Injection

## What is SQL Injection?

**SQL injection \(SQLi\)** is an application security weakness that allows attackers to control an application’s database – letting them access or delete data, change an application’s data-driven behavior, and do other undesirable things – by tricking the application into sending unexpected SQL commands. SQL injections are among the most frequent threats to data security.

## Login Page SQL Injection

To check for potential SQL injection vulnerabilities we have entered a single quote in to the "Name" field and submitted the request using the "Login" button.

## How to Prevent against SQL Injection Attacks

An organization can adopt the following policy to protect itself against SQL Injection attacks.

* **User input should never be trusted -** It must always be sanitized before it is used in dynamic SQL statements.
* **Stored procedures –** these can encapsulate the SQL statements and treat all input as parameters.
* **Prepared statements –**prepared statements to work by creating the SQL statement first then treating all submitted user data as parameters. This has no effect on the syntax of the SQL statement.
* **Regular expressions –**these can be used to detect potential harmful code and remove it before executing the SQL statements.
* **Database connection user access rights –**only necessary access rights should be given to accounts used to connect to the database. This can help reduce what the SQL statements can perform on the server.
* **Error messages –**these should not reveal sensitive information and where exactly an error occurred. Simple custom error messages such as “Sorry, we are experiencing technical errors. The technical team has been contacted. Please try again later” can be used instead of display the SQL statements that caused the error.

script that executes on open that would ping alternate server on a console.log

scan to see if document has 

4 or 5 

sql injects url browser

document with active link

can 



Finding the vulnerability in a website

inurl:faq.php

intitle:"sign in"



{% embed url="http://demo.testfire.net/" %}

username: jsmith

password: demo1234

* Say someone figures out a persons username. Someone can put a `'` after the username which is telling the system that we have ended the user input, then you can put a `SQL` comment character `--` \(dash dash\) after the `'` and what this does is comment out everything after this command sequence after the username, and something that is commonly after a username is a password check and by doing so bypasses the password allowing access to a users account. 

`jsmith'--` 



