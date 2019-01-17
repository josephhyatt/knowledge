# Ruby/Rails Cheat Sheet

In Rails, there are different conventions for the:

1. **File name** \(outside\) e.g. orders\_controller.rb
2. **File definition** \(inside\) e.g. OrdersController
3. **File location** \(inside\) e.g. /app/controllers

## Rails Naming Convention

Rails use the same naming convention as Ruby \(for a list of the Ruby naming conventions scroll down\) with some additions:

**Variable** - _e.g. order\_amount, total_  
Variables are named where all letters are lowercase and words are separated by underscores.

**Class and Module** - _e.g. InvoiceItem_  
Classes and modules use MixedCase and have no underscores, each word starts with a uppercase letter.

**Database Table** - _e.g. invoice\_items, orders_ Table names have all lowercase letters and underscores between words, also all table names need to be plural.

**Model** - _e.g. Order_  
The model is named using the class naming convention of unbroken MixedCase and is always the singular of the table name. e.g.

* Table name might be orders \(plural\)
* The model name would be Order \(singular\)
* Rails will then look for the class definition in a file called order.rb in the /app/models directory.
* If the model class name has multiple capitalised words, the table name is assumed to have underscores between these words.

**Controller** - _e.g. OrdersController_  
Controller class names are pluralized, such that **OrdersController would be the controller class for the orders table**. Rails will then look for the class definition in a file called orders\_controller.rb in the /app/controllers directory.

**Files, Directories and other pluralization**  
Files are named using lowercase and underscores. Assuming we have an Orders controller then the following other conventions will apply:

* That there is a helper module named **OrdersHelper** in the **orders\_helper.rb** found in the app/helpers directory.
* Rails will look for view template files for the controller in the **app/views/orders** directory.
* Output from this view will then be used in the layout defined in the **orders.html.erb** in the **app/views/layouts** directory.
* Test files including **order\_test.rb** will be created in the **/test/unit** directory, a file will be created in the **/test/fixtures**directory called **orders.yml** and finally a file called **orders\_controller\_test.rb** will be created in the **/test/functional directory**

**Primary Key**  
The primary key of a table is assumed to be named id.

**Foreign Key**  
The foreign key is named with the singular version of the target table name with \_id appended to it, e.g. order\_id in the items table where we have items linked to the orders table.

**Many to Many Link Tables**  
Tables used to join two tables in a many to many relationship is named using the table names they link, with the table names in alphabetical order, for example items\_orders.

**Automated Record Timestamps**  
You can get ActiveRecord to automatically update the create and update times of records in a database table. To do this create two specially named columns created\_at and updated\_at to your table, i.e. t.datetime :created\_at and t.datetime :updated\_at. If you only want to store the date rather than a date and time, use :created\_on and :updated\_on.

## Naming Convention Summary

### Model Naming Convention

```text
Table: 			orders
Class: 			Order
File: 			/app/models/order.rb
Primary Key: 	id
Foreign Key: 	customer_id
Link Tables: 	items_orders
```

### Controller Naming Convention

```text
Class: 			OrdersController
File: 			/app/controllers/orders_controller.rb
Layout: 		/app/layouts/orders.html.erb
```

### View Naming Convention

```text
Helper: 		/app/helpers/orders_helper.rb
Helper Module: 	OrdersHelper
Views: 			/app/views/orders/… (list.html.erb for example)
```

### Tests Naming Convention

```text
Unit: 			/test/unit/order_test.rb
Functional: 	/test/functional/orders_controller_test.rb
Fixtures: 		/test/fixtures/orders.yml
```

### The Ruby Naming Conventions

_As Jon would say, ProTip:_

> Ruby uses the first character of the name to help it determine it’s intended use.

## **Local Variables**

> These should be a lowercase letter followed by other characters, naming convention states that it is better to use underscores rather than **camelBack** for multiple word names, `e.g. mileage, variable_xyz`

## **Instance Variables**

> Instance variables are defined using the **single "at" sign \(@\) followed by a name**. It is suggested that a lowercase letter should be used after the **@**, `e.g. @colour`

## **Instance Methods**

> Method names should start with a lowercase letter, and may be followed by digits, underscores, and letters, `e.g. paint, close_the_door`

## **Class Variables**

> Class variable names start with a **double "at" sign \(@@\) and may be followed by digits, underscores, and letters**, `e.g. @@colour`

## **Constant**

> Constant names start with an uppercase letter followed by other characters. Constant objects are by convention named using all uppercase letters and underscores between words, `e.g. THIS_IS_A_CONSTANT`

## **Class and Module**

> Class and module names starts with an uppercase letter, by convention they are named using MixedCase, `e.g. module Encryption, class MixedCase`

## **Global Variables**

> Starts with a dollar \($\) sign followed by other characters, `e.g. $global`

