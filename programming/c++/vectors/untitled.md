# Vector Overview

C-style arrays in C and C++ are not dynamic - the compiler needs to know the size of the array \(the type and number of elements\) in order to properly allocate memory. This is quite different to [interpreted languages](https://en.wikipedia.org/wiki/Interpreted_language) like Python, PHP and JavaScript, where arrays are inherently dynamic - you don’t need to specify data type and size in advance.

Vectors in C++ are standard containers which provide powerful dynamic-array like functionality, with fixed-time access to elements in any order. Vectors are defined by a template class available in the [standard library](https://en.wikipedia.org/wiki/C%2B%2B_Standard_Library) - you just need to add `#include <vector>` to your header file to have access to vector functionality.

A C++ vector can be described as a dynamic C-style array - with fast and efficient access to individual elements in any order. You don’t need to worry about memory and size allocation. Subscripting \(i.e. `myVector[]`\) access is provided as with C-style arrays.

Vectors work by setting up an initial memory allocation for your data. If more data is added and the allocation is exceeded, the vector class creates a new, bigger array in memory. The old array is copied across to the new, before being deleted. This is all abstracted away so you don’t need to worry about it, though you should probably take measures to minimise re-allocation - which will help maximise performance.

**This article is an ongoing summary of my notes on functions in C++. Please don’t assume that what you read here is accurate. For a more complete description of vectors in C++, check the references presented below.**

## DECLARATION

Include the appropiate header to give access to the vector class. Then declare the vector - which shoudl specify the data type that will be contained by the vector:

```cpp
#include <vector>

// Define a vector that will contain integers
std::vector<int> myIntsContainer;

// Define a vector that will contain doubles
std::vector<double> myDoublesContainer;
```

For convenience, you can use a `typedef` statement to make declarations more concise:

```cpp
// Set up aliases
typedef std::vector<int> intVec;
typedef std::vector<double> doubleVec;

// Declarations
intVec myIntsContainer;
doubleVec myDoublesContainer;
```

## INITIALIZING

To initialize, you can use an initializer list provided your compiler supports this. This method works with g++ version 5.4.0 on Ubnuntu, compiling with the `c++11` flag.

```cpp
// Method 1
std::vector<int> myVec {1,3,5};

// Method 2 (equivalent to method 1)
std::vector<int> myAltVec = {2,4,6};
```

You can also specify the initial size during the declaration, and only set values later:

```cpp
// Specify size in the vector constructor.
// This works with int data type, but will cause problems with aggregate data types.
// See the std::vector::reserve() method
std::vector<int> myVec(3)
myVec = {7,8,9};

// You can still dynamically add elements, even though the size was specified during initialisation
myVec.push_back(10); // myVec is now {7,8,9,10}

...
```

The [reserve\(\) method](http://www.cplusplus.com/reference/vector/vector/reserve/) is a better option for specifying an original size rather than using the vector constructor, which will cause problems when the vector holds aggregate data:

```cpp
#include <iostream>
#include <vector>

int main(int argc, char const *argv[])
{
    struct KeyVal {
        std::string key;
        int val;
    };
    std::vector<KeyVal> options;

    // Set the capacity for this vector
    options.reserve(10);

    // Add initial data
    options = {
        {"Option 1", 1},
        {"Option 2", 2},
        {"Option 3", 3}
    };

    // Up to 7 more elements can be added with re-allocation
    options.push_back({"Option 4", 4});

    for(KeyVal& option : options) {
        std::cout << option.key << ": " << option.val << std::endl;
    }
    return 0;
}
```

## ADDING ELEMENTS

The `vector.assign(n, el)` method overwrites the vector, such that it contains `n` elements, each defined by `el`.

The `vector.push_back(el)` method appends an element to the vector.

To add an element to a position specified by an iterator use `vector.insert()`.

Examples:

```cpp
// Define an empty vector `doubleContainer` that will contain the double data type
std::vector<double> doubleContainer;

// Assign
// -----------------------------------------------------------------------------
// Populate the vector with 10 elements, each with a value of 3.14159
doubleContainer.assign(10, 3.14159);

// The original vector will be over-written by assign
doubleContainer.assign(3, 9.806); // {9.806, 9.806, 9.806}

// Append
// -----------------------------------------------------------------------------
doubleContainer.push_back(3.14159); // {9.806, 9.806, 9.806, 3.14159}

// Insert - requires an iterator
// -----------------------------------------------------------------------------
// Create an iterator for the vector
std::vector<double>::iterator it;

// Set a position for the iterator - in this case, after the first element
it = doubleContainer.begin() + 1;

// Insert a value
doubleContainer.insert(it, 5.601); // {9.806, 5.601, 9.806, 9.806, 3.14159}

...
```

Note that:

* `assign()` overwrites the vector
* `insert()` requires an iterator as first parameter, not a simple index
* `push_back()` appends to the vector

## ADD ELEMENTS AT A PRECISE POSITION

```cpp
struct User {
      int id; std::string name;
};
std::vector<User> users;

// emplace() requires an iterator
std::vector<User>::iterator uIt = users.begin();
users.emplace(uIt, User{42, "David"});

// The iterator relating to this container is invalidated by `emplace()`.
// To call `emplace()` again, the iterator must be reset.
uIt = users.begin();
users.emplace(uIt + 1, User{444, "Elaine"});

for(User& u : users) {
    std::cout << "Name: " << u.name << ", ID: " << u.id << std::endl;
}
```

Note that if a reallocation is triggered by `emplace()` \(i.e. the allocated memory block grows\), all iterators, pointers and references for the container are invalidated. If no reallocation occurs, only those pointing to the position and beyond are invalidated. All iterators, pointers and references to elements before position keep referring to the same elements they were referring to before the `emplace()` call.

## MORE EFFICIENT APPENDING

The `vector::emplace_back()` function inserts a new element at the end of the vector.

**The new element is constructed in place using the provided arguments.** This avoids a copy action, improving efficiency as compared with `push_back()`.

The allocated storage space will only be extended if the new vector size exceeds the current vector capacity.

When the vector element is made up of aggregate data \(like a struct\), the benefits of `emplace_back()` vs `push_back()` may be negated. In this case, you should use an initialiser list constructor in the data structure, which will allow the new element to be constructed in-place without a copy.

```cpp
// `emplace_back()` with aggregate data
// -------------------------------------------------------------------------
struct Book {
    // Initialiser list constructor.
    Book(int id, std::string title, std::string author): id(id), title(title), author(author) {}
    int id;
    std::string title;
    std::string author;
};

// Initialise a vector of Books
std::vector<Book> books;

// Reserve memory - vector will hold up to 20 elements before re-allocation is necessary
books.reserve(20);

// When using `push_back()`, a temporary object of appropriate type is created and initialized
books.push_back({ 456, "A Scanner Darkly", "Philip K Dick", 15.99 });

// ...has the same performance as `push_back()`, because a temporary `Book` is constructed:
books.emplace_back(Book{ 777, "Guards Guards!", "Terry Pratchett", 9.99 });

// However, the following works if the Struct has an initialiser list constructor:
books.emplace_back(999, "Idoru", "William Gibson", 9.99);
```

## CLEAR

The `clear()` method removes all elements:

```cpp
// Populate the vector with 10 elements, each with a value of 3.14159
doubleContainer.assign(10, 3.14159); // `doubleContainer` now has 10 elements

doubleContainer.clear(); // `doubleContainer` now has 0 elements

...
```

## ERASE

Deletes a single element from a vector.

```cpp
std::vector<int> intArray;

// Add 10 elements to the vector
for(int i = 0; i <= 10; i++) {
    intArray.push_back(i);
}

// intArray vector is now {0,1,2,3,4,5,6,7,8,9}

// Delete 5th element
intArray.erase(intArray.begin() + 4);

// intAarray vector is now {0,1,2,3,5,6,7,8,9}
...
```

## OPTIMIZATION

When the memory allocated for your vector is exceeded as the vector grows, a re-allocation is triggered. Re-allocation is resource-expensive and should be avoided if possible.

One simple way of avoiding unnecessary reallocation is to set a rational capacity for the vector with [vector.reserve\(\)](http://www.cplusplus.com/reference/vector/vector/reserve/). If you do this, re-allocation won’t occur until you exceed the defined reserve.

The method `vector.reserve(n)` sets the vector capacity such that n elements can be contained. If `n` is greater than the current vector capacity the container storage will be reallocated, increasing its capacity to `n` \(or greater\). `vector.reserve()` has no effect on vector size and does not alter the vector elements.

If `n` is less than the current capacity the function call does not cause a reallocation and the vector capacity is not affected.

