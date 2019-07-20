# Create Application

## SQLite

```ruby
#### If you want to use SQLite (not recommended)
rails new myapp
```

## MySQL

```ruby
#### If you want to use MySQL
rails new myapp -d mysql

```

## PostgreSQL

```ruby
#### If you want to use Postgres
# Note that this will expect a postgres user with the same username
# as your app, you may need to edit config/database.yml to match the
# user you created earlier
rails new myapp -d postgresql
```

## Setting Up PostgreSQL

```ruby
sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ xenial-pgdg main' > /etc/apt/sources.list.d/pgdg.list"
wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install postgresql-common
sudo apt-get install postgresql-9.5 libpq-dev
```

> The postgres installation doesn't setup a user for you, so you'll need to follow these steps to create a user with permission to create databases. Feel free to replace `joseph` with your username.

```ruby
sudo -u postgres createuser joseph -s

# If you would like to set a password for the user, you can do the following
sudo -u postgres psql
postgres=# \password joseph
```

