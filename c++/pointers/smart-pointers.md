# Smart Pointers

## Smart Pointers <a id="smartpointers"></a>

* There are **4** types of **Smart Pointers:** Unique Pointer `unique_ptr`, Shared Pointers `shared_ptr`, Weak Pointers `weak_ptr`, Auto Pointers `auto_ptr`. 
* Smart pointers are objects.
* Smart pointers are implemented as c++ template classes \(like `vector` templates\) which can be instantiated.
* Smart pointers can **ONLY** point to heap-allocated memory.
* Smart pointers call **delete** when no longer needed.
* Smart pointers adhere to **RAII \(Resource Acquisition Is Initialization\)** principles. First RAII objects get allocated on the stack. **RA \(Resource Acquisition\)** object will acquire some resource, such as opening a file allocating memory that acquires a lock, an so forth. RAI**I** **\(Initialization\)**, means the resources acquired an object initialization time \(which happens in the objects constructor\). At some point the need to **relinquish that resource** that was required and that happens in the destructor.

## unique\_ptr <a id="typesofsmartpointers"></a>

* Unique Pointers `(unique_ptr)` - simple smart pointer, very efficient!  `unique_ptr<T>`
  * points to an object of type `T` on the heap.
  * it's unique - there can only be **ONE** `unique_ptr<T>` pointing to the object on the heap
  * **owns** what it points to
  * **cannot** be assigned or copied
  * **cannot** be moved
  * when the pointer is **destroyed**, what it points to is automatically destroyed

```cpp
// unique_ptr - creating, initializing and using
{
    std::unique_ptr<int> p1 { new int {100} }; 
    std::cout << *p1 << std::endl;  // 100
    *p1 = 200;
    std::cout << *p1 << std::endl;  // 200
}  // automatically deleted
```

```cpp
// unique_ptr - some other useful methods
{
    std::unique_ptr<int> p1 { new int {100} };
    std::cout << *p1.get() << std::endl;  // 0x564388
    *p1.reset();  // p1 is now nullptr
    if (p1)  // checks if pointer p1 is initialized
    std::cout << *p1 << std::endl;  // won't execute
}  // automatically deleted
```

```cpp
// unique_ptr - user defined classes
{
    std::unique_ptr<Account> p1 { new Account {"Larry} }; // unique_ptr manage Account object on the heap
    std::cout << *p1 << std::endl;  // display account
    p1->deposit(1000);
    p1->deposit(500);
} // automatically deleted
```

```cpp
// unique_ptr - vectors and move
{
    std::vector<std::unique_ptr<int>> vec; // unique_ptr manage Account object on the heap
    std::unique_ptr<int> ptr { new int{100} };
    vec.push_back(ptr);  // Error - copy not allowed
    vec.push_back(std::move(ptr));  // giving ownership of pointer to vector and ptr will be set to null pointer
} // automatically deleted
```

```cpp
// unique_ptr - make_unique function (C++14) returns a unique pointer of the specified type and allows it to pass initialization values into the constructor for the managed object
{
    std::unique_ptr<int> p1 = make_unique<int>(100);  // 
    std::unique_ptr<Account> p2 = make_unique<Account>("Curly", 5000);  // display account
    auto p3 = = make_unique<Player>("Hero", 100, 100);
} // automatically deleted
```

* Shared Pointers `(shared_ptr)`
* Weak Pointers `(weak_ptr)`
* Auto Pointers `(auto_ptr)`

## How To Create A Smart Pointer <a id="howtocreateasmartpointer"></a>

* `#include <memory>`

```cpp
// smart pointer 'ptr' will manage an object of type `Some_Class` that's been allocated on the heap.
// after smart pointer object is create you can use the dereference operator, the member select operator, or any of the other smart pointer member methods.
{
std::smart_pointer_type<Some_Class> ptr = ...

    ptr -> method();
    std::cout << (*ptr) << endl;
}
// pointer will auto delete when no longer needed
```

## Can't Be Done Using Smart Pointers <a id="cantbedoneusingsmartpointers"></a>

* Can't do pointer arithmetic on smart pointers like you can with raw pointers.

