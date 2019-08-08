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

## 4 Most Common Types of SQL Injections

* **In-band SQL Injection \(SQLi\)**
  * **Error-based SQL Injection**:
    * Cause:
      * Relies on error messages thrown by the database server to obtain information about the structure of the database. 
  * **UNION-based SQL Injection**:
    * Cause:
      * Using UNION SQL operator to combine the results of two or more SELECT statements into a single result, which is then returned as part of the HTTP response.
* **Inferential SQL Injection \(Blind SQLi\)**
  * **Boolean-based SQL Injection**:
    * Cause: When an application is forced to return a different result depending on whether the query returns a TRUE or FALSE result. Based on the result, the content within the HTTP response will change, or remain the same.
  * **Time-based SQL Injection**:
    * Cause:
      * When sending an SQL query to the database, which forces the database to wait for a specified amount of time \(in seconds\) before responding. The time website takes to respond will indicate to the attacker whether the result of the query is TRUE or FALSE.

## Prevent or Mitigate SQL Injection Attacks



1. **Use parameterized queries:** \(think "variables"\) Parameterized queries force the developer to first define all the SQL code, and then pass in each parameter to the query later. This coding style allows the database to distinguish between code and data, regardless of what user input is supplied.
2. **Trust no-one:** Assume all user-submitted data is trying to attack you. Apply input validations such as `mysql_real_escape_string ()` to make sure that any malicious characters haven't passed to a SQL query through data. Than sanitize each data by filtering user data by context. For instance, email addresses must be filtered to enable only the characters allowed in email addresses or cell phone numbers must be filtered to allow for only the digits enabled in a phone number and so forth.
3. **Don't use dynamic SQL when it can be avoided:** Frequently, the data sanitization techniques could fail, so apply prepared statements, stored procedures or parameterized queries whenever you can. But, consider the fact that while stored procedures restrict some SQLi types, they slip to guard vs. many others, so don’t depend only on their use for your protection.
4. **Update and patch**: Vulnerabilities in databases and apps that fraudsters can take advantage of have commonly identified, so it's crucial to use patches and updates whenever possible.
5. **Firewall:** Consider a Web Application Firewall \(WAF\) – whether softer or appliance-based is an excellent solution to filter out malicious data. A firewall can be especially useful to serve some security protection versus a new vulnerability before a patch is available.
6. **Reduce your attack surface:** Get rid of any database functionality that you don't need to prevent a hacker taking advantage of it. 
7. **Apply sufficient privileges:** Avoid connecting your database through an account with admin-level privileges except you have some strong reason. Using a restricted account is a safer option, and can reduce an attacker malicious executes.
8. **Limited error message:** Assume that your application is not secure and act accordingly by encrypting or hashing passwords and other confidential data including connection strings so attackers can't figure out your database architecture through error messages, make sure that they only provide minimal info.
9. **Permanently maintain SQL statements from database-connected apps:** This will provide to detect fake SQL vulnerabilities and comments. Supervising tools that exploit computer learning or behavioral analyses can be beneficial.
10. **Don't forget the basics:** Change the passwords of application accounts into the database regularly. This is common sense, but in practice these passwords often stay unchanged for months or even years.
11. **Use better software:** Make coders responsible for checking the code and for fixing security flaws in custom applications before the software is delivered.

