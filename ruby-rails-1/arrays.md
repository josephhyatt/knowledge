# Arrays

## Create an Array

```ruby
array = []                    # Array; zero-based indexing
array = Array.new(5)          # Array with size 
array = Array.new(2, "abc")   # ["abc", "abc"]
array = Array(0..9)           # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

## Most commonly used methods with arrays

```ruby
array.size                            # Array size
array.length                          # Array size
array.count                           # Array size
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

