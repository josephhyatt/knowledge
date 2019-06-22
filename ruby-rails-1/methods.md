# Methods

A **method** is a set of expressions that returns a value. With **methods**, one can organize their code into subroutines that can be easily invoked from other areas of their program. Other languages sometimes refer to this as a **function**. A **method** may be defined as a part of a class or separately.

## Create new array and iterate through array squaring each element before pushing it to new array and return new array

```ruby
# created a new empty array arr.
# iterate through the other array array which is passed as an argument, squaring each element before pushing it (using <<) into our new array arr.
# Finally we return the newly created array arr by simply writing arr as the final line in the method block.
def square_array(array)
  arr = []
  array.each { |i| arr << i ** 2 }
  return arr
end
```

## Return a name in a sentence

```ruby
# a badge_maker method that, when provided a persons name, will create and return this message:
def badge_maker(name)
  Return “Hello, my name is #{name}.”
end
```

## Takes an array of names and returns an array

```ruby
# write a batch_badge_creator method that takes an array of names as an argument and returns an array of badge messages:

def badge_maker(speakers)
  speakers.map { |speaker| “Hello, my name is #{speaker}.” }
end
```

## Assign each argument with only 1 parameter 

```ruby
# Write a method called assign_rooms that takes the list of speakers and assigns each speaker to a room. Make sure that each room only has one speaker:
def assign_rooms(speakers)
  Speakers.each_with_index.map do | speaker, room |
    “Hello, #{speaker}! "You’ll be assigned to room #{room + 1}!”
  end
end
```

## Outputs a messages to screen

```ruby
# Create a method called printer that will output first the results of the batch_badge_creator method and then of the assign_rooms method to the screen:
def printer(speakers)
  batch_badge_creator(speakers).each do |badge|
    puts badge
  end
  assign_rooms(speakers).each do |assignment|
    puts assignment
  end
end
```

## Keep place and show everyone their current location in line

```ruby
# Build the line method that shows everyone their current place in the line. If there is nobody in line, it should say "The line is currently empty.".
# Build a method that a new customer will use when entering the deli. The take_a_numbermethod should accept two arguments, the array for the current line of people (katz_deli), #and a string containing the name of the person wishing to join the line. The method should return the persons name along with their position in line. Top-Tip: Remember that #people like to count from 1, not from 0 ("zero") like computers. Build the now_serving method which should call out (i.e. puts) the next person in line and then remove them #from the front. If there is nobody in line, it should call out (puts) that "There is nobody waiting to be served!".
def line(katz_deli)
  if katz_deli.length == 0
    puts “The line is currently empty.”
  else
    line_list = “The line is currently:”
    katz_deli.each_with_index do | person, index |
      line_list << “ #{index + 1). #{person}”
    end
    puts line_list
  end
end

def take_a_number(katz_deli, person)
  katz_deli << person
  puts “Welcome, #{person}. You are number #{katz_deli.length} in line.”
end

def now_serving(katz_deli)
  if katz_deli.length == 0
    puts “There is nobody waiting to be served!”
  else
    Puts “Currently serving #{katz_deli[0]0}
    katz_deli.shift
  end
end
```

## Takes an argument\(array\) of string elements and convert it into a string

```ruby
# Write a method oxford_comma that takes an argument array of string elements 
# and converts it into a string using the Oxford comma.
def oxford_coma(array)
  if array.length == 1
    array.join
  elsif array.length == 2
    array.join( “ and “)
  else array.length >= 3
    array[0..-2].join(“, “) + “, and “ + array[-1]
  end
end
```

## Reverse and return each word in a sentence

```ruby
# Write a method called reverse_each_word that takes in a string argument of a sentence 
# and returns that same sentence with each word reversed in place.
def reverse_each_word(string)
  string.split(“ “).collect { |word| word.reverse }.join(“ “)
end
```

## Only return greeting if block starts with "T" or "t"  

```ruby
# Only put out a greeting if the word we pass into the block starts with the letter "T".
def hello_t(array)
  i = 0
  new_arr = []
  while i < array.length
    if (array[i].start_with?(“T”) || array[i].start_with?(“t”))
      yield(array[i])
        new_arr << array[i]
      end
      i += 1
    end
    new_arr
end

# calling the method hello_t
hello_t([“Tim”, “Tom”, “Jim”]) { |name| puts “Hi, #{name}” }
```

## Pass each element of a collection to a block

```ruby
#Define a method that uses yield and a while loop to pass each element of a collection to a block.
def my_each(array)
  i = 0
  while i < array.length
    yield array[i]
    i += 1
  end
  array
end
```

## Iterate over an array and yielding each member of the array into a block

```ruby
# We are using a while loop to iterate over an array and yielding each member of the array in turn to a block:

def hello(array)
  i = 0
  while i < array.length
    yield(array[i])
    i += 1
  end
end

#We would call our method like this:
hello([“Tim”, “Tom”, “Jim”]) { |name| puts “Hi, #{name}” }
```

## Push the return values using yield into empty array and return new array at the end

```ruby
# We are setting a variable, collection, equal to an empty array.
# Then, inside our while loop, we push the return value of using yield(array[i]) into that collection array and return that new collection at the end:
def hello(array)
  i = 0
  collection = []
  while i < array.length
    collection << yield(array[i])
    i += 1
  end
  collection
end
```

## Yields members of an array to a block

```ruby
# Build a method that yields members of a collection to a block.
def my_collect(collection)
  mod_collection = []
  i = 0
  while i < collection.length
    mod_collection << yield(collection[i])
    i += 1
  end
  mod_collection
end
```

