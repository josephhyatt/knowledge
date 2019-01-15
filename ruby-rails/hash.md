# Hash

> Hashes associate a **key** to some **value**. You may then retrieve the value based upon its key. Hashes can map from anything to anything! You can map from Strings to Numbers, Strings to Strings, Numbers to Boolean's… and you can mix all of those. Symbols are especially common as keys. Symbols look like this :symbol. A symbol is a colon followed by some characters. You can think of them as special strings that stand for \(symbolize\) something! We often use symbols because Ruby runs faster when we use symbols instead of strings.

## **Create** Hash

> You create a hash by **surrounding** the **key-value pairs** with **curly braces**. The arrow always goes from the key to the value depicting the meaning: "This key points to this value.". Key-value pairs are then separated by commas.

```ruby
hash = {}     # New Hash without default value
```

```ruby
{key => value} # Syntax

{:hobby => "programming"}

{ 42 => "answer", 
 "score" => 100,
  :name => "Tobi" }
```

## Accessing a Hash

> **Accessing** an entry in a hash looks a lot like accessing it in an array. However **with a hash the key can be anything**, not just numbers. If you try to access a key that does not exist, the value nil is returned, which is Ruby's way of saying "nothing", because if it doesn't recognize the key it can't return a value for it.

```ruby
hash[key] # Syntax

hash = { 
  :key => "value" 
}

hash[:key] # => "value"
hash[foo] # => nil
```

#### Assigning Values to a Hash

> Assigning values to a hash is similar to assigning values to an array. With a hash, the key can be a number or it can be a symbol, string, number... or anything.

```ruby
hash[key] = value # Syntax

hash = { 
  :a => "b"
}

hash[:key] = "value"

hash # => {
  :a=>"b", 
  :key=>"value"
}
```

## Deleting Key From Hash

> Delete a specified key from the hash, so that the key and its value can not be accessed.

```ruby
hash.delete(key) # Syntax

hash = {
  :a => "b", 
  :b => 10
}

hash.delete(:a)
hash # => {:b=>10}
```

## Most common hash methods

```ruby
hash = Hash.new("default_value")  # New hash with a default value for any key
hash.default = "another_value"    # Changes default value
hash.size                         # Hash size
hash.length                       # Hash size
hash.count                        # Hash size
hash[1]                           # Get the value or default if key not found
hash.clear                        # Removes all key-value pairs from hash
hash.delete(1)                    # Deletes a key-value pair by key
hash.empty?                       # Test if hash is empty (true or false)
hash.invert                       # New hash with inverted key-value pairs
hash.values                       # Returns a new array containing all the values of hash.
```

#### 



