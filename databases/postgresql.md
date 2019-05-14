# PostgreSQL

**CREATING POSTGRESQL USERS**

A default PostgresSQL installation always includes the _postgres_ superuser. Initially, you must connect to PostgreSQL as the _postgres_ user until you create other users \(which are also referred to as _roles_\).

To create a PostgreSQL user, follow these steps:

1. At the command line, type the following command as the server's **root** user:

   ```text
   sudo -u postgres -i
   ```

2. You can now run commands as the PostgreSQL superuser. To create a user, type the following command:  


   ```text
   createuser --interactive --pwprompt
   ```

3. At the Enter name of role to add: prompt, type the user's name.
4. At the Enter password for new role: prompt, type a password for the user.
5. At the Enter it again: prompt, retype the password.
6. At the Shall the new role be a superuser? prompt, type y if you want to grant superuser access. Otherwise, type n.
7. At the Shall the new role be allowed to create databases? prompt, type y if you want to allow the user to create new databases. Otherwise, type n.
8. At the Shall the new role be allowed to create more new roles? prompt, type y if you want to allow the user to create new users. Otherwise, type n.
9. PostgreSQL creates the user with the settings you specified.

**CREATING POSTGRESQL DATABASES**

To create a PostgreSQL database, follow these steps:

1. At the command line, type the following command as the server's **root** user:

   ```text
   sudo -u postgres -i
   ```

2. You can now run commands as the PostgreSQL superuser. To create a database, type the following command. Replace _user_with the name of the user that you want to own the database, and replace _dbname_ with the name of the database that you want to create:  


   ```text
   createdb -O user dbname
   ```

   * PostgreSQL users that have permission to create databases can do so from their own accounts by typing the following command, where _dbname_ is the name of the database to create:

     ```text
     createdb dbname
     ```

**ADDING AN EXISTING USER TO A DATABASE**

To grant an existing user privileges to a database, follow these steps:

1. Run the _psql_ program as the database's owner, or as the _postgres_ superuser.
2. Type the following command. Replace _permissions_ with the permissions you want to grant, _dbname_ with the name of the database, and _username_ with the user:

   ```text
   GRANT permissions ON DATABASE dbname TO username;
   ```

   For detailed information about the access privileges that are available in PostgreSQL, please visit [http://www.postgresql.org/docs/9.1/static/sql-grant.html](http://www.postgresql.org/docs/9.1/static/sql-grant.html).

3. The user can now access the database with the specified permissions.

**DELETING POSTGRESQL DATABASES**

Similar to the _createdb_ command for creating databases, there is the _dropdb_ command for deleting databases. To delete a database, you must be the owner or have superuser privileges.

Type the following command, replacing _dbname_ with the name of the database that you want to delete:

```text
dropdb dbname
```

The _dropdb_ program does not ask for confirmation before deleting a database. As soon as you press Enter, PostgreSQL deletes the database and all of the data it contains.

**DELETING POSTGRESQL USERS**

Similar to the _createuser_ command for creating users, there is the _dropuser_ command for deleting users.

To delete a specific user, type the following command. Replace _username_ with the name of the user that you want to delete:

```text
dropuser username
```

If the user owns any databases or other objects, you cannot drop the user. Instead, you receive an error message similar to the following:

```text
dropuser: removal of role "username" failed: ERROR:  role "username" cannot be dropped because some objects depend on it
DETAIL:  owner of database dbname
```

You should change the database's owner \(or drop the database entirely\), and then you can drop the user.

