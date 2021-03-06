# Ruby/Rails Cheat Sheet

In Rails, there are different conventions for the:

1. **File name** \(outside\) e.g. orders\_controller.rb
2. **File definition** \(inside\) e.g. OrdersController
3. **File location** \(inside\) e.g. /app/controllers

## Rails Naming Convention

Rails use the same naming convention as Ruby \(for a list of the Ruby naming conventions scroll down\) with some additions:

**Variable** - `order_amount` _`total`_  
Variables are named where all letters are lowercase and words are separated by underscores.

**Class and Module** - `InvoiceItem`  
Classes and modules use MixedCase and have no underscores, each word starts with a uppercase letter.

**Database Table** - `invoice_items` _orders_ Table names have all lowercase letters and underscores between words, also all table names need to be plural.

**Model** - `Order`  
The model is named using the class naming convention of unbroken MixedCase and is always the singular of the table name. e.g.

* Table name might be orders \(plural\)
* The model name would be Order \(singular\)
* Rails will then look for the class definition in a file called order.rb in the /app/models directory.
* If the model class name has multiple capitalised words, the table name is assumed to have underscores between these words.

**Controller** - `OrdersController`  
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

## **Global Variables**

> Starts with a dollar \($\) sign followed by other characters

```ruby
$age = 21
$name = "Joseph"
```

## **Local Variables**

> These should be a lowercase letter followed by other characters, naming convention states that it is better to use underscores rather than **camelBack** for multiple word names

```ruby
_age = 21
_name = "Joseph"
```

## **Instance Variables**

> Instance variables are defined using the **single "at" sign \(@\) followed by a name**. It is suggested that a lowercase letter should be used after the **@**

```ruby
@age = 21
```

## **Constants**

> Constant names start with an uppercase letter followed by other characters. Constant objects are by convention named using all uppercase letters and underscores between words

```ruby
AGE = 21 # constant; by convention - constants can be modified and generate a warning
```

## **Class Variables**

> Class variable names start with a double "at" sign `(@@)` and may be followed by digits, underscores, and letters.

```ruby
class Car
    @make
    @@wheels = 4

    def initialize(make)
        @make = make
    end

    def self.wheels
        @@wheels
    end
    attr_accessor :make
end

#outside the class
civic = Car.new("Honda")

#instance variable, called on the object
>> civic.make
=> "Honda"
#class variable, called on the class itself
>> Car.wheels
=> 4
```

## **Instance Methods**

> Instance Methods can only be called on a particular instance of the class. You use Instance Methods when you need to act on a particular instance of the class. This is often when the functionality concerns the identity of the instance such as calling properties on the object, or invoking behavior.

```ruby
class Basket  
  def self.find(id)  
    puts "finding basket with the id of #{id}"  
  end

  def products  
    []  
  end  
end  

# in the rails console
basket = Basket.new  
=> #<Basket:0x007fd2e446c7b0>

basket.products  
=> []  
```

## **Class Method**

> A Class Method is a method that is defined on the class. In this example I’ve defined a `find` method on the `Basket` class that accepts an `id`. You should use Class Methods when the functionality you are writing does not belong to an instance of that class.

```ruby
class Basket  
  def self.find(id) # self signifies that this method is a Class Method. 
    puts "finding basket with the id of #{id}"  
  end  
end

# to use this method
basket = Basket.find(‘abc’)  
```

## Functions

> A function is a block of code that can be called from another location in the program or class. It is used to reduce the repetition of multiple lines of code. A function can either return nil, a value, or an array of values. If multiple items are returned, they will be returned as an array.

```ruby
# Syntax
# standard functions
# if within a class, called on the object
def functionName(passedParameters)

   # code to be executed

   # optional return value or variable
   return value
   # another way to return value
   value
end
```

```ruby
# Example
def absolute_value(x)
    if x < 0
        x = x * -1
    end
    return x
end
```

## Blocks

> A block contains code that can be executed. Blocks are not objects, but there are methods that can be used on blocks for repetition and local variable purposes.

```ruby
# Syntax
# x is a local variable which represents a parameter passed into a block
# one way to write a block
{ |x|
    # code to be executed
}

# other way to do it
do |x|
    # code to be executed
end
```

```ruby
# Example
10.times { puts "This code will execute 10 times!" }
```

## Collect

> Applies a block onto every item in an array. Collect does not modify an array, rather it returns a copy.

```ruby
# Syntax
array.collect { |element| #code to run on element }
```

```ruby
# Example
numberLine = [ 1, 2, 3, 4, 5 ]
shiftedNumberLine = numberLine.collect { |number| number + 1 }

# Output =>
shiftedNumberLine is [2, 3, 4, 5, 6]

```

