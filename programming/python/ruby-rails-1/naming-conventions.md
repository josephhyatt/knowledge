# Naming Conventions

## General Ruby conventions

> Class names are `CamelCase`.

> Methods and variables are `snake_case`.

> Methods with a `?` suffix will return a boolean.

> Methods with a `!` suffix mean one of two things: either the method operates destructively in some fashion, or it will raise and exception instead of failing \(such as Rails models' `#save!` vs. `#save`\).

> In documentation, `::method_name` denotes a _class method_, while `#method_name` denotes a _instance method_.

## Database

> _Database tables_ use `snake_case`. Table names are **plural**.

> _Column names_ in the database use `snake_case`, but are generally **singular**.

> **Example:**

```text
+--------------------------+
| bigfoot_sightings        |
+------------+-------------+
| id         | ID          |
| sighted_at | DATETIME    |
| location   | STRING      |
| profile_id | FOREIGN KEY |
+------------+-------------+

+------------------------------+
| profiles                     |
+---------------------+--------+
| id                  | ID     |
| name                | STRING |
| years_of_experience | INT    |
+---------------------+--------+
```

## Model

> Model _class names_ use `CamelCase`. These are **singular**, and will map automatically to the plural database table name.

> Model _attributes_ and _methods_ use `snake_case` and match the column names in the database.

> Model files go in `app/models/#{singular_model_name}.rb`.

> **Example:**

```text
# app/models/bigfoot_sighting.rb
class BigfootSighting < ActiveRecord::Base
  # This class will have these attributes: id, sighted_at, location
end
```

```text
# app/models/profile.rb
class Profile < ActiveRecord::Base
  # Methods follow the same conventions as attributes
  def veteran_hunter?
    years_of_experience > 2
  end
end
```

### Relations in models

> Relations use `snake_case` and follow the type of relation, so `has_one` and `belongs_to` are **singular** while `has_many` is **plural**.

> Rails expects foreign keys in the database to have an `_id` suffix, and will map relations to those keys automatically if the names line up.

> **Example:**

```text
# app/models/bigfoot_sighting.rb
class BigfootSighting < ActiveRecord::Base
  # This knows to use the profile_id field in the database
  belongs_to :profile
end
```

```text
# app/models/profile.rb
class Profile < ActiveRecord::Base
  # This knows to look at the BigfootSighting class and find the foreign key in that table
  has_many :bigfoot_sightings
end
```

## Controllers

> Controller _class names_ use `CamelCase` and have `Controller` as a suffix. The `Controller` suffix is always singular. The name of the resource is usually **plural**.

> Controller _actions_ use `snake_case` and usually match the standard route names Rails defines \(`index`, `show`, `new`, `create`, `edit`, `update`, `delete`\).

> Controller files go in `app/controllers/#{resource_name}_controller.rb`.

> **Example:**

```text
# app/controllers/bigfoot_sightings_controller.rb
BigfootSightingsController < ApplicationController
  def index
    # ...
  end
  def show
    # ...
  end
  # etc
end
```

```text
# app/controllers/profiles_controller.rb
ProfilesController < ApplicationController
  def show
    # ...
  end
  # etc
end
```

## Routes

> Route names are `snake_case`, and usually match the controller. Most of the time routes are **plural** and use the plural `resources`.

> [Singular routes](http://edgeguides.rubyonrails.org/routing.html#singular-resources) are a special case. These use the singular `resource` and a singular resource name. However, they still map to a plural controller by default!

> **Example:**

```text
resources :bigfoot_sightings
# Users can only see their own profiles, so we'll use `/profile` instead
# of putting an id in the URL.
resource :profile
```

## Views

> View file names, by default, match the controller and action that they are tied to.

> Views go in `app/views/#{resource_name}/#{action_name}.html.erb`.

> **Examples:**

```text
app/views/bigfoot_sightings/index.html.erb
app/views/bigfoot_sightings/show.html.erb
app/views/profile/show.html.erb
```

