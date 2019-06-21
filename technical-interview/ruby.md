# Ruby

## Class

* A **class** blueprint from which objects are created. The **object** is also called as an _instance of a class_.

```ruby
  class MyClass
    def some_method
    end
  end
```

## Arrays

An array is a Ruby data type that holds an ordered collection of values, which can be any type of object including other arrays.

## Blocks

A block is a chunk of code that lives inside a control statement, loop, method definition, or method call. It returns the value of its last line. In Ruby, blocks can be created two ways: with braces or with a do/end statement.

## LOGICAL OPERATORS

Logical operators are used to compare to boolean values. Ruby has 6 operators to compare boolean values: `and`, `or`, `not`, `&&`, `||`, and `not`.

## COMPARISON OPERATORS

Comparison operators are used to test the relationship between two objects. The equality \(`==`\) and inequality \(`!=`\) operators can be used on almost any type of value where the other operators are used for numeric comparisons.

## Hashes

Hashes are collections of key-value pairs. Like arrays, they have values associated with indices, but in the case of hashes, the indices are called “keys.” Keys can be anything that’s hashable, such as integers, strings, or symbols, but they must be unique for the hash they belong. The values to which keys refer can be any Ruby object.

## if, unless, elsif and else

* An **IF** statement takes a boolean expression and executes certain code only if the boolean expression evaluates to true.
* **Unless** is the opposite of an if statement. The statement takes a boolean expression and executes certain code only if the boolean expression evaluates to false.
* **Elsif** is a conditional statement used to manage a program’s control flow.
* **Else** which runs certain code only if the previous conditional statements do not run.

## Loops

* a **while** loop that will execute a block of code as long as its condition is true. When the condition becomes false, the code after the end of the loop will be executed.
* an **until loop** that will execute a block of code as long as its condition is false. When the condition becomes true, the code after the end of the loop will be executed.
* a **for** loop is used to iterate an object.

## Methods

* **methods** are used to create parameterized, reusable code.

```text
def method_name(arguments)
  # Code to be executed
end
```

## Puts vs. Print

* **puts** adds a newline after executing, and **print** does not.

## Variables

* Variables are assigned values using the `=` operator. A variable can hold almost any type of value including numbers, strings, arrays, and hashes.
* **Instance Variables** - Instance variables are created for each class instance and are accessible only within that instance. They are accessed using the @ operator. Outside of the class definition, the value of an instance variable can only be read or modified via that instance's public methods.

```ruby
  class MyClass
    @one = 1
    def do_something
      @one = 2
    end
    def output
      puts @one
    end
  end
```

* **Class Variables** - These variables are associated with the class hierarchy rather than any object instance of the class and are the same across all object instances. Class variables are accessed using the @@ operator.

```ruby
class MyClass
    @@value = 1
    def add_one
      @@value= @@value + 1
    end
    
    def value
      @@value
    end
  end
```

## Inheritance

* A **class** can **inherit functionality and variables** from a **superclass**, sometimes referred to as a **parent class or base class**.

