# Sets and Maps

## std::set

std::set is an associative container and header that need to be include for it is,  
`#include<set>`

### Benefits and Features of std::set:

* It’s doesn’t allow duplicate elements i.e. it only contains unique elements.
* Std::set can contain element of any specified type in template argument i.e.
* std::set internally store elements in balanced binary tree.

```cpp
std::set<int> // contains only int elements.
class Sample;
std::set<Sample> // contains only Sample class objects.
```

* By default std::set uses the operator &lt; for comparing two elements and but if user passes the external sorting criteria i.e. comparator then it uses that instead of default operator &lt;.
* std::set will keep the inserted elements in sorted order based on the assigned sorting criteria i.e. either by default criteria operator &lt; or by passed comparator \(if passed\).

**Basic Example:**

```cpp
#include <iostream>
#include<set>
#include<string>

int main()
{
	std::set<std::string> setOfNumbers;
 
	// Lets insert four elements
	setOfNumbers.insert("first");
	setOfNumbers.insert("second");
	setOfNumbers.insert("third");
	setOfNumbers.insert("first");
 
	// Only 3 elements will be inserted
	std::cout<<"Set Size = "<<setOfNumbers.size()<<std::endl;
 
	// Iterate through all the elements in a set and display the value.
	for (std::set<std::string>::iterator it=setOfNumbers.begin(); it!=setOfNumbers.end(); ++it)
	    std::cout << ' ' << *it;
	std::cout<<"\n";
	return 0;
}

/*
Output:
Set Size = 3
first second third
*/
```

`setOfNumbers.size()` in above example returns 3 because std::set only contains unique elements, so string “first” was added in the set only once and call to again insert “first” string was rejected.

It uses the operator &lt; for comparison and keeps the all the elements in sorted order, in output above you can check that all strings are in sorted order.

### How to iterate through std::set:

You can use **iterators** i.e.

```cpp
for (std::set<std::string>::iterator it=setOfNumbers.begin(); it!=setOfNumbers.end(); ++it)
std::cout << ' ' << *it;
```

But you cannot modify the elements using iterators because if you modify the element value then internal data structure of `std::set` will get corrupt and it will not remain balanced binary search tree. Hence further additions and find operations will not work properly.

### How to search an element in std::set:

Using find member function,

_iterator find \(const value\_type& val\) const;_

It Searches the container for an element equivalent to val and returns an iterator to it if found, otherwise it returns an iterator to `set::end`

`std::set` **find** example

```cpp
#include<iostream>
#include<set>
#include<string>

int main()
{
	std::set<std::string> setOfNumbers;
 
	// Lets insert four elements
	setOfNumbers.insert("first");
	setOfNumbers.insert("second");
	setOfNumbers.insert("third");
	setOfNumbers.insert("first");
 
	// Search for element in set using find member function
	std::set<std::string>::iterator it = setOfNumbers.find("second");
	if(it != setOfNumbers.end())
		std::cout<<"'first'  found"<<std::endl;
	else
		std::cout<<"'first' not found"<<std::endl;
 
	// Search for element in set using find member function
	it = setOfNumbers.find("fourth");
	if(it != setOfNumbers.end())
		std::cout<<"'fourth'  found"<<std::endl;
	else
		std::cout<<"'fourth' not found"<<std::endl;
 
	return 0;
}

/*
Output:
‘first’ found
‘fourth’ not found
*/
```

### Why should we use std::set::find member method instead of std::find standard generic algorithm?

Because find member function knows its internal data structure is balance binary search tree and hence designed to operate on that only therefore it will take much lesser time then standard algorithm `std::find`

### How std::set verifies while insertion if element is already added or not:

By default `std::set` uses the operator `<` 

It internally maintains a binary balanced tree and during insertion it compares the new element with already present nodes and finds the right position of new element in tree. If that element is already present then it doesn’t insert the new element.

But wait a minute, if it uses the operator &lt; for comparison of two elements then how it checks if two elements are equal or not with operator &lt; ?

It uses the following logic to check if two elements like a and b are equal or not,

If `a < b` is false and `b` `< a` is false  
Then it means a and b are equal.

Example to verify insertion in `std::set`

```cpp
#include<iostream>
#include<set>

std::set<int> setOfNumbers;
void checkAndInsert(int num)
{
  if(setOfNumbers.insert(num).second)
     std::cout<<"Number "<<num<<" inserted sucessfuly\n";
 else
     std::cout<<"Number "<<num<<" was already present in set\n";
 
}
int main()
{
    checkAndInsert(2);
    checkAndInsert(3);
    checkAndInsert(2);
    checkAndInsert(1);
 
   // Check the size of set
   std::cout<<setOfNumbers.size()<<std::endl;
 
   // Iterate through all the elements in a set and display the value.
   for (std::set<int>::iterator it=setOfNumbers.begin(); it!=setOfNumbers.end(); ++it)
      std::cout << ' ' << *it;
   std::cout<<"\n";
 return 0;
}

/*
Output:
Number 2 inserted sucessfuly
Number 3 inserted sucessfuly
Number 2 was already present in set
Number 1 inserted sucessfuly
3
1 2 3
*/
```

### How to remove an element in std::set :

Using member function erase i.e.

There are **three overloaded versions of erase member function**

```cpp
iterator  erase (const_iterator position);
size_type erase (const value_type& val);
iterator  erase (const_iterator first, const_iterator last);
```

Let’s see an example to **erase element** in `std::set`

```cpp
#include<iostream>
#include<set>
#include<string>

int main()
{
 
	std::set<std::string> setOfNumbers;
 
	// Lets insert four elements
	setOfNumbers.insert("first");
	setOfNumbers.insert("second");
	setOfNumbers.insert("third");
	setOfNumbers.insert("first");
 
	// Iterate through all the elements in a set and display the value.
	for (std::set<std::string>::iterator it=setOfNumbers.begin(); it!=setOfNumbers.end(); ++it)
	    std::cout << ' ' << *it;
 
	std::cout<<std::endl;
 
	setOfNumbers.erase("third");
 
	// Iterate through all the elements in a set and display the value.
	for (std::set<std::string>::iterator it=setOfNumbers.begin(); it!=setOfNumbers.end(); ++it)
		    std::cout << ' ' << *it;
 
	std::cout<<std::endl;
	return 0;
}

/*
Output:
first second third
first second
*/
```

## std::map

**Maps** are used to replicate associative arrays. Maps contain sorted **key-value** pair, in which each key is unique and cannot be changed, and it can be inserted or deleted but cannot be altered. Value associated with keys can be altered. We can search, remove and insert in a map within `O(n)` time complexity.

![](https://www.studytonight.com/cpp/images/map-example.png)

### **Benefits of using std::map :**

* It stores only unique keys and that too in sorted order based on its assigned sorting criteria.
* As keys are in sorted order therefore searching element in map through key is very fast i.e. it takes logarithmic time.
* In `std::map` there will be only one value attached with the every key.
* `std::map` can be used as associative arrays.
* It might be implemented using balanced binary trees.

Lets see an example

```cpp
#include <map>
#include <string>
#include <iterator>
 
int main()
{
    std::map<std::string, int> mapOfWords;
    // Inserting data in std::map
    mapOfWords.insert(std::make_pair("earth", 1));
    mapOfWords.insert(std::make_pair("moon", 2));
    mapOfWords["sun"] = 3;
    // Will replace the value of already added key i.e. earth
    mapOfWords["earth"] = 4;
    // Iterate through all elements in std::map
    std::map<std::string, int>::iterator it = mapOfWords.begin();
    while(it != mapOfWords.end())
    {
        std::cout<<it->first<<" :: "<<it->second<<std::endl;
        it++;
    }
    // Check if insertion is successful or not
    if(mapOfWords.insert(std::make_pair("earth", 1)).second == false)
    {
        std::cout<<"Element with key 'earth' not inserted because already existed"<<std::endl;
    }
    // Searching element in std::map by key.
    if(mapOfWords.find("sun") != mapOfWords.end())
        std::cout<<"word 'sun' found"<<std::endl;
    if(mapOfWords.find("mars") == mapOfWords.end())
        std::cout<<"word 'mars' not found"<<std::endl;
    return 0;
}

/* Output:
earth :: 4
moon :: 2
sun :: 3
Element with key ‘earth’ not inserted because already existed
word ‘sun’ found
word ‘mars’ not found
*/
```

### **Creating std::map objects**

Creating a `std::map` of words i.e.

Key = Word \(`std::string`\)  
Value = Word’s frequency count \(`int`\)

```cpp
std::map<std::string, int> mapOfWords;
```

As no external sorting criteria for key\(`std::string`\) is specified in above `std::map`, therefore it will use default key sorting criteria i.e operator &lt; and all elements will be arranged inside std::map in alphabetical sorted order of keys.

### **Inserting data in std::map :**

Inserting data using insert member function,

```cpp
mapOfWords.insert(std::make_pair("earth", 1));
mapOfWords.insert(std::make_pair("moon", 2));
```

We can also insert data in std::map using operator \[\] i.e.

```cpp
mapOfWords["sun"] = 3;
```

### **Different between operator \[\] and insert function:**

If specified key already existed in map then operator \[\] will silently change its value where as insert will not replace already added key instead it returns the information i.e. if element is added or not. e.g.

```cpp
mapOfWords["earth"] = 4; // Will replace the value of already added key.
```

Where as for insert member function,

```cpp
mapOfWords.insert(std::make_pair("earth", 1)).second
```

will return false.

### **Iterating through all std::map elements:**

```cpp
std::map<std::string, int>::iterator it = mapOfWords.begin();
while(it != mapOfWords.end())
{
std::cout<<it->first<<" :: "<<it->second<<std::endl;
it++;
}
```

Each entry in `std::map<std::string, int>` is `std::pair<std::string, int>` therefore through iterator, key can be accessed by it-&gt;first and value by it-&gt;second 

### **Searching element in std::map by key**

find member function of `std::map` can be used to search element in `std::map` by key. If specified key is not present then it returns the `std::map::end` else an iterator to the searched element.

```cpp
iterator find (const key_type& k);
 
//e.g.
 
if(mapOfWords.find("sun") != mapOfWords.end())
std::cout<<"word 'sun' found"<<std::endl;
if(mapOfWords.find("mars") == mapOfWords.end())
std::cout<<"word 'mars' not found"<<std::endl;
```

### **Searching element in std::map by Value**

To search element in `std::map` by value we need to iterate through all of the elements and check for the passed value and return i.e.

```cpp
#include <iostream>
#include <map>
#include <string>
#include <iterator>
 
std::map<std::string, int>::iterator serachByValue(std::map<std::string, int> & mapOfWords, int val)
{
    // Iterate through all elements in std::map and search for the passed element
    std::map<std::string, int>::iterator it = mapOfWords.begin();
    while(it != mapOfWords.end())
    {
        if(it->second == val)
        return it;
        it++;
    }
}
int main()
{
    std::map<std::string, int> mapOfWords;
    // Inserting data in std::map
    mapOfWords.insert(std::make_pair("earth", 1));
    mapOfWords.insert(std::make_pair("moon", 2));
    mapOfWords["sun"] = 3;
 
    std::map<std::string, int>::iterator it = serachByValue(mapOfWords, 3);
    if(it != mapOfWords.end())
        std::cout<<it->first<<" :: "<<it->second<<std::endl;
 
return 0;
}

/* output:
sun :: 3
/*
```

### **Deleting data from std::map**

`std::map`’s erase member function is used to delete the element in `std::map`

```cpp
void erase (iterator position);
size_type erase (const key_type& k);
void erase (iterator first, iterator last);
```

**Code example**

```cpp
#include <map>
#include <string>
#include <iterator>
int main()
{
    std::map<std::string, int> mapOfWords;
    mapOfWords.insert(std::make_pair("earth", 1));
    mapOfWords.insert(std::make_pair("moon", 2));
    mapOfWords["sun"] = 3;
 
    // Erasing By iterator
    std::map<std::string, int>::iterator it = mapOfWords.find("moon");
    mapOfWords.erase(it);
 
    // Erasing By Key
    mapOfWords.erase("earth");
 
    return 0;
}
```

#### `begin`, `end` and `find`

begin, end and find returns an iterator. `begin()` returns the iterator to the starting entry of the map, `end()` returns the iterator next to the last entry in the map and `find()` returns the iterator to the entry having key equal to given key \(passed as parameter\).

![begin, end and find function for maps](https://www.studytonight.com/cpp/images/begin-find-end-functions.png)

