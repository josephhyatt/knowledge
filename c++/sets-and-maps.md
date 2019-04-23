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

For example: A map of students where **roll number** is the key and **name** is the value can be represented graphically as :

![](https://www.studytonight.com/cpp/images/map-example.png)

Notice that keys are arranged in ascending order, its because maps always arrange its keys in sorted order. In case the keys are of string type, they are sorted lexicographically.

### Creating a Map in C++ STL

Maps can easily be created using the following statement :

```cpp
map<key_type , value_type> map_name;
```

This will create a map with key of type **Key\_type** and value of type **value\_type**. One thing which is to remembered is that key of a map and corresponding values are always inserted as a pair, you cannot insert only key or just a value in a map.

Here is a program that will illustrate creating a map in different ways:

```cpp
#include <iostream>
#include <map>

using namespace std;

int main ()
{
    map<int,int> m{ {1,2} , {2,3} , {3,4} };
    /* creates a map m with keys 1,2,3 and 
        their corresponding values 2,3,4 */  
    
    map<string,int> map1; 
    /*  creates a map with keys of type character and 
      values of type integer */
    
    map1["abc"]=100;    // inserts key = "abc" with value = 100
    map1["b"]=200;      // inserts key = "b" with value = 200
    map1["c"]=300;      // inserts key = "c" with value = 300
    map1["def"]=400;    // inserts key = "def" with value = 400
    
    map<char,int> map2 (map1.begin(), map1.end());
    /* creates a map map2 which have entries copied 
        from map1.begin() to map1.end() */ 
    
    map<char,int> map3 (m);
    /* creates map map3 which is a copy of map m */
}
```

#### Member Functions of Map in C++ STL

Following are some of the commonly used function of Map container in STL:

#### `at` and `[ ]`

Both **at** and `[ ]` are used for accessing the elements in the map. The only difference between them is that **at** throws an exception if the accessed key is not present in the map, on the other hand operator `[ ]` inserts the key in the map if the key is not present already in the map.

```text
#include <iostream>
#include <map>

using namespace std;

int main ()
{
    map<int,string> m{ {1,”nikhilesh”} , {2,”shrikant”} , {3,”ashish”} };
    
    
    cout << m.at(1) ;  // prints value associated with key 1 ,i.e nikhilesh
    cout << m.at(2) ;  // prints value associated with key 2 ,i.e shrikant
    
    /* note that the parameters in the above at() are the keys not the index */
    
    cout << m[3] ; // prints value associated with key 3 , i.e ashish
    
    
    
    m.at(1) = "vikas";   // changes the value associated with key 1 to vikas
    m[2] = "navneet";   // changes the value associated with key 2 to navneet
    
    m[4] = "doodrah";   
    /* since there is no key with value 4 in the map, 
        it insert a key-value pair in map with key=4 and value = doodrah */
    
    m.at(5) = "umeshwa"; 
    /* since there is no key with value 5 in the map , 
     it throws an exception  */  
}
```

#### `empty`, `size` and `max_size`

`empty()` returns boolean true if the map is empty, else it returns Boolean false. `size()` returns number of entries in the map, an entry consist of a key and a value. `max_size()` returns the upper bound of the entries that a map can contain \(maximum possible entries\) based on the memory allocated to the map.

#### `insert` and `insert_or_assign`

`insert()` is used to insert entries in the map. Since keys are unique in a map, it first checks that whether the given key is already present in the map or not, if it is present the entry is not inserted in the map and the iterator to the existing key is returned otherwise new entry is inserted in the map.

There are two variations of insert\(\):

* `insert(pair)` : In this variation, a pair of key and value is inserted in the map. The inserted pair is always inserted at the appropriate position as keys are arranged in sorted order.
* `insert(start_itr , end_itr)`: This variation inserts the entries in range defined by **start\_itr** and **end\_itr** of another map.

The `insert_or_assing()` works exactly as insert\(\) except that if the given key is already present in the map then its value is modified.

```cpp
#include <iostream>
#include <map>

using namespace std;

int main ()
{
    map<int,int> m{{1,2} , {2,3} , {3,4} };
    
    m.insert( pair<int,int> (4,5));
    /* inserts a new entry of key = 4 and value = 5 in map m */
    
    /* make_pair() can also be used for creating a pair */
    m.insert( make_pair(5, 6));
    /* inserts a new entry of key = 5 and value = 6 */
    
    
    map::iterator i , j;
    i = m.find(2);    // points to entry having key =2
    j = m.find(5);    // points to entry having key =5
    
    map<int,int> new_m;
    
    new_m.insert(i,j);
     /* insert all the entries which are pointed 
     by iterator i to iterator j*/ 
    
    m.insert( make_pair(3,6));  
     // do not insert the pair as map m already contain key = 3 */ 
    
    m.insert_or_assign( make_pair(3,6));  // assign value = 6 to key =3   
}
```

#### `erase` and `clear`

`erase()` removes the entry from the map pointed by the iterator \(which is passed as parameter\), however if we want to remove all the elements from the map, we can use `clear()`, it clears the map and sets its size to 0.

There are two variations of erase :

* `erase(iterator_itr)` : This removes entry from the map pointed by iterator **iterator\_itr**, reducing the size of map by 1.
* `erase(start_iterator, end_iterator)` : It removes the elements in range specified by the **start\_iterator** and **end\_iterator**.

#### `begin`, `end` and `find`

begin, end and find returns an iterator. `begin()` returns the iterator to the starting entry of the map, `end()` returns the iterator next to the last entry in the map and `find()` returns the iterator to the entry having key equal to given key \(passed as parameter\).

![begin, end and find function for maps](https://www.studytonight.com/cpp/images/begin-find-end-functions.png)

