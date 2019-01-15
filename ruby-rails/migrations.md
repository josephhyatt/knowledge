# Migrations

> A **migration** is a file that contains a specific set of instructions for the database. Rails introduces a specific Domain-specific language for writing instructions for how a database should be created. For example, last week we created a migration file to create the articles table with columns for title and body. When this migration file is run, Rails will be able to make the changes to the database and automatically create the table for us.

## **Create Migration with Columns**

```ruby
rails g migration CreatTablename columnname:columntype    # Syntax

rails g migration CreateAuthors first_name:string last_name:string email:string birthday:date age:integer
```

> Will **create**

```ruby
class CreateAuthors < ActiveRecord::Migration[5.0]
  def change
    create_table :authors do |t|
      t.string :first_name
      t.string :last_name
      t.string :email
      t.date :birthday
      t.integer :age
      t.timestamps
    end
  end
end
```

## Change Column Name for Existing Table 

> To change column `channel` to `Section` in table **channels**

```ruby
 run rails g migration rename_channel_to_section
```

> Creates this **migration**

```ruby
class RenameChannelToName < ActiveRecord::Migration[5.2]
  def change
  end
end
```

> Then add code in `change` method in the new migration file in `db/migrate` `rename_column :channels, :channel, :name`

```ruby
class RenameChannelToName < ActiveRecord::Migration[5.2]
  def change
    rename_column :channels, :channel, :name
  end
end
```

## **One Line Migration to Drop DB Columns**

```ruby
rails generate migration RemoveFieldNameFromTableName field_name:datatype    # Syntax

rails generate migration RemoveNameFromMerchant name:string
```

> Will **create**

```ruby
class RemoveNameFromMerchant < ActiveRecord::Migration
  def change
    remove_column :merchants, :name, :string
  end
end
```

## Drop DB Table

```ruby
rails generate migration DropMerchantsTable    # Will drop Merchants table from the DB
```

## Most Common CLI Migration Methods

```ruby
db:create                     # creates the database for the current env 
db:create:all                 # creates the databases for all envs 
db:drop                       # drops the database for the current env 
db:drop:all                   # drops the databases for all envs 
db:drop db:create db:migrate  # This will destroy your db and then create it and then migrate your current schema 
db:migrate                    # runs migrations for the current env that have not run yet 
db:migrate:up                 # runs one specific migration 
db:migrate:down               # rolls back one specific migration 
db:migrate:status             # shows current migration status 
db:rollback                   # rolls back the last migration 
db:forward                    # advances the current schema version to the next one 
db:seed                       # (only) runs the db/seed.rb file 
db:schema:load                # loads the schema into the current env's database 
db:schema:dump                # dumps the current env's schema (and seems to create the db as well) 
db:setup                      # runs db:schema:load, db:seed 
db:reset db:migrate           # This will reset your database and reload your current schema with all 
db:migrate:redo               # runs (db:migrate:down db:migrate:up) or (db:rollback db:migrate) depending on the specified migration 
db:migrate:reset              # runs db:drop db:create db:migrate 
```

