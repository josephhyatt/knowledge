# Arrays

> An [array](https://en.wikipedia.org/wiki/Array) is a collection of elements, by default an array of n elements has its **index** enumerated from 0 to n-1, i.e, the index to the first element of an array is 0

## Create an Array

```ruby
array = []                    # Array; zero-based indexing
array = Array.new(5)          # Array with size 
array = Array.new(2, "abc")   # ["abc", "abc"]
array = Array(0..9)           # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

```ruby
a = [4,6,7,5]  # simple array declaration 
a.length     # => 4
a.rotate     # => [6, 7, 5, 4]
a.sort      # => [4, 5, 6, 7]
a.sort.reverse  # => [7, 6, 5, 4]
a[0]       # => 4
a[3]       # => 5
a[4] = 3     # => 3 ;resulting array is [4, 6, 7, 5, 3]
a << 1      # => [4, 6, 7, 5, 3, 1] ; useful when array size is unknown
a[10] = 0    # => 0 ;resulting array is [4, 6, 7, 5, 3, 1, nil, nil, nil, nil, 0]
a.length     # => 11
```

## Most commonly used methods with arrays

```ruby
array.size                            # Array size
array.length                          # Array size
array.count                           # Array size
array.reverse                         # This method reverses an array.
array.first                           # Returns the first element of the array
array.last                            # Returns the last element of the array
array.inspect                         # Returns a readable list of what’s items are in the array.
array.at(5)                           # Element at index 5
array.push(42)                        # Add 42 to end of array
array.pop                             # Remove last element from array
array.shift                           # Remove first element from array
array.unshift(15)                     # Add 15 to beginning of array
array.include?("abc")                 # Return true if the value is present in array
array.take(2)                         # Return the first n itens of the array
array.drop(2)                         # Drops first n elements from array and returns the rest of the elements as a new array
array.index("abc")                    # Return index of "abc" in array or nil if not found
array.sort                            # Return a new sorted array
array.sort!                           # Perform a sort operation in array directly
array.delete("abc")                   # Delete all items in array that are equals to obj "abc" given as parameter. Return last item deleted or nil if item was not found 
array.insert(1, "xyz")                # Inserts the given values before the element with the given index. Needed to pass index and objects as parameters
array.empty?                          # Return true if the array has no elements
array.uniq                            # Return a new array removing duplicated values
array.uniq!                           # Remove duplicated values from array 
array.methods.sort - Object.methods   # List all Array instance methods
array = %w{a b c #{num}}              # ["a", "b", "c", "\#{num}"]
array = %W{a b c #{num}}              # ["a", "b", "c", "5"] (if num = 5)
```

## Iterate Through Array

```ruby
#created a new empty array arr.
#iterate through the other array array which is passed as an argument, squaring each element before pushing it (using <<) into our new array arr.
#Finally we return the newly created array arr by simply writing arr as the final line in the method block.
def square_array(array)
  arr = []
  array.each { |i| arr << i ** 2 }
  return arr
end
```

## Takes Array of Names and Returns Another Array

```ruby
#Write a batch_badge_creator method that takes an array of names as an argument and returns an array of badge messages:
def badge_maker(speakers)
  speakers.map { |speaker| “Hello, my name is #{speaker}.” }
end
```

## Takes List and Assigns Each Item to New Parameter

```ruby
#Write a method called assign_rooms that takes the list of speakers and assigns each speaker to a room. Make sure that each room only has one speaker:
def assign_rooms(speakers)
  Speakers.each_with_index.map do | speaker, room |
    “Hello, #{speaker}! "You’ll be assigned to room #{room + 1}!”
  end
end
```

## 

