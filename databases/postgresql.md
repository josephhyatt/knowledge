# PostgreSQL

**Login as ROOT user**

* `sudo -u postgres -i`

## Creating a PostgreSQL Database

**Step 1: Login as the Postgres User**

`su - postgres`

**Step 2: Enter the PostgreSQL Environment**

`psql`

With the **psql** command, you’ll be greeted by its current version and command prompt.

`psql (9.5.14)  
Type "help" for help.  
postgres=#`

**Step 3: Creating the PostgreSQL Database**

Let’s create our first database by typing in the command below.  Replace dbname with the database name of your choice.

`CREATE DATABASE dbname;`

## Listing a PostgreSQL Database

**Verify Creation of PostgreSQL Database**

Using the following command allows us to view the databases in our PostgreSQL instance \(you can ignore, delete or utilize the default databases: postgres, template0, template1\)

`postgres=# \list`

## **Deleting a PostgreSQL Database**

Once you’ve backed up your removing your PostgreSQL database is a cinch!  Its similar to creating a database but we will be using the drop command. In my command line example, the database name is “**dbname**”. By using the list command in the previous section, you’ll be able to view your databases’ names. Replace dbname with your database’s name in the command below.

`DROP DATABASE dbname;`

