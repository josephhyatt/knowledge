# Vectors

Vectors are same as dynamic arrays with the ability to resize itself automatically when an element is inserted or deleted, with their storage being handled automatically by the container. Vector elements are placed in contiguous storage so that they can be accessed and traversed using iterators. In vectors, data is inserted at the end. Inserting at the end takes differential time, as sometimes there may be a need of extending the array. Removing the last element takes only constant time because no resizing happens. Inserting and erasing at the beginning or in the middle is linear in time.

## Iterators

1. [begin\(\)](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/) – Returns an iterator pointing to the first element in the vector
2. [end\(\)](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/) – Returns an iterator pointing to the theoretical element that follows the last element in the vector
3. [rbegin\(\)](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/) – Returns a reverse iterator pointing to the last element in the vector \(reverse beginning\). It moves from last to first element
4. [rend\(\)](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/) – Returns a reverse iterator pointing to the theoretical element preceding the first element in the vector \(considered as reverse end\)
5. [cbegin\(\)](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/) – Returns a constant iterator pointing to the first element in the vector.
6. [cend\(\)](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/) – Returns a constant iterator pointing to the theoretical element that follows the last element in the vector.
7. [crbegin\(\)](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/) – Returns a constant reverse iterator pointing to the last element in the vector \(reverse beginning\). It moves from last to first element
8. [crend\(\)](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/) – Returns a constant reverse iterator pointing to the theoretical element preceding the first element in the vector \(considered as reverse end\)

```cpp
#include <iostream> 
#include <vector> 
  
using namespace std; 
  
int main() 
{ 
    vector<int> g1; 
  
    for (int i = 1; i <= 5; i++) 
        g1.push_back(i); 
  
    cout << "Output of begin and end: "; 
    for (auto i = g1.begin(); i != g1.end(); ++i) 
        cout << *i << " "; 
  
    cout << "\nOutput of cbegin and cend: "; 
    for (auto i = g1.cbegin(); i != g1.cend(); ++i) 
        cout << *i << " "; 
  
    cout << "\nOutput of rbegin and rend: "; 
    for (auto ir = g1.rbegin(); ir != g1.rend(); ++ir) 
        cout << *ir << " "; 
  
    cout << "\nOutput of crbegin and crend : "; 
    for (auto ir = g1.crbegin(); ir != g1.crend(); ++ir) 
        cout << *ir << " "; 
  
    return 0; 
} 
// Output:
Output of begin and end: 1 2 3 4 5 
Output of cbegin and cend: 1 2 3 4 5 
Output of rbegin and rend: 5 4 3 2 1 
Output of crbegin and crend : 5 4 3 2 1
```

## Capacity

1. [size\(\)](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/) – Returns the number of elements in the vector.
2. [max\_size\(\)](https://www.geeksforgeeks.org/vector-max_size-function-in-c-stl/) – Returns the maximum number of elements that the vector can hold.
3. [capacity\(\)](https://www.geeksforgeeks.org/vector-capacity-function-in-c-stl/) – Returns the size of the storage space currently allocated to the vector expressed as number of elements.
4. [resize\(\)](https://www.geeksforgeeks.org/vector-resize-c-stl/) – Resizes the container so that it contains ‘g’ elements.
5. [empty\(\)](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/) – Returns whether the container is empty.
6. [shrink\_to\_fit\(\)](https://www.geeksforgeeks.org/vector-shrink_to_fit-function-in-c-stl/) – Reduces the capacity of the container to fit its size and destroys all elements beyond the capacity.
7. [reserve\(\) ](https://www.geeksforgeeks.org/using-stdvectorreserve-whenever-possible/)– Requests that the vector capacity be at least enough to contain n elements.

```text
#include <iostream> 
#include <vector> 
  
using namespace std; 
  
int main() 
{ 
    vector<int> g1; 
  
    for (int i = 1; i <= 5; i++) 
        g1.push_back(i); 
  
    cout << "Size : " << g1.size(); 
    cout << "\nCapacity : " << g1.capacity(); 
    cout << "\nMax_Size : " << g1.max_size(); 
  
    // resizes the vector size to 4 
    g1.resize(4); 
  
    // prints the vector size after resize() 
    cout << "\nSize : " << g1.size(); 
  
    // checks if the vector is empty or not 
    if (g1.empty() == false) 
        cout << "\nVector is not empty"; 
    else
        cout << "\nVector is empty"; 
  
    // Shrinks the vector 
    g1.shrink_to_fit(); 
    cout << "\nVector elements are: "; 
    for (auto it = g1.begin(); it != g1.end(); it++) 
        cout << *it << " "; 
  
    return 0; 
} 
Output:
Size : 5
Capacity : 8
Max_Size : 4611686018427387903
Size : 4
Vector is not empty
Vector elements are: 1 2 3 4
```

## Element Access

1. [reference operator \[g\]](https://www.geeksforgeeks.org/vectoroperator-vectoroperator-c-stl/) – Returns a reference to the element at position ‘g’ in the vector
2. [at\(g\)](https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/) – Returns a reference to the element at position ‘g’ in the vector
3. [front\(\)](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/) – Returns a reference to the first element in the vector
4. [back\(\)](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/) – Returns a reference to the last element in the vector
5. [data\(\)](https://www.geeksforgeeks.org/vector-data-function-in-c-stl/) – Returns a direct pointer to the memory array used internally by the vector to store its owned elements.

```cpp
#include <bits/stdc++.h> 
using namespace std; 
  
int main() 
{ 
    vector<int> g1; 
  
    for (int i = 1; i <= 10; i++) 
        g1.push_back(i * 10); 
  
    cout << "\nReference operator [g] : g1[2] = " << g1[2]; 
  
    cout << "\nat : g1.at(4) = " << g1.at(4); 
  
    cout << "\nfront() : g1.front() = " << g1.front(); 
  
    cout << "\nback() : g1.back() = " << g1.back(); 
  
    // pointer to the first element 
    int* pos = g1.data(); 
  
    cout << "\nThe first element is " << *pos; 
    return 0; 
} 

// Output:
Reference operator [g] : g1[2] = 30
at : g1.at(4) = 50
front() : g1.front() = 10
back() : g1.back() = 100
The first element is 10
```

## Modifiers

1. [assign\(\) ](https://www.geeksforgeeks.org/vector-assign-in-c-stl/)– It assigns new value to the vector elements by replacing old ones
2. [push\_back\(\)](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) – It push the elements into a vector from the back
3. [pop\_back\(\)](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) – It is used to pop or remove elements from a vector from the back.
4. insert\(\) – It inserts new elements before the element at the specified position
5. [erase\(\)](https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/) – It is used to remove elements from a container from the specified position or range.
6. [swap\(\)](https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/) – It is used to swap the contents of one vector with another vector of same type. Sizes may differ.
7. [clear\(\)](https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/) – It is used to remove all the elements of the vector container
8. [emplace\(\)](https://www.geeksforgeeks.org/vector-emplace-function-in-c-stl/) – It extends the container by inserting new element at position
9. [emplace\_back\(\)](https://www.geeksforgeeks.org/vectoremplace_back-c-stl/) – It is used to insert a new element into the vector container, the new element is added to the end of the vector

```cpp
#include <bits/stdc++.h> 
#include <vector> 
using namespace std; 
  
int main() 
{ 
    // Assign vector 
    vector<int> v; 
  
    // fill the array with 10 five times 
    v.assign(5, 10); 
  
    cout << "The vector elements are: "; 
    for (int i = 0; i < v.size(); i++) 
        cout << v[i] << " "; 
  
    // inserts 15 to the last position 
    v.push_back(15); 
    int n = v.size(); 
    cout << "\nThe last element is: " << v[n - 1]; 
  
    // removes last element 
    v.pop_back(); 
  
    // prints the vector 
    cout << "\nThe vector elements are: "; 
    for (int i = 0; i < v.size(); i++) 
        cout << v[i] << " "; 
  
    // inserts 5 at the beginning 
    v.insert(v.begin(), 5); 
  
    cout << "\nThe first element is: " << v[0]; 
  
    // removes the first element 
    v.erase(v.begin()); 
  
    cout << "\nThe first element is: " << v[0]; 
  
    // inserts at the beginning 
    v.emplace(v.begin(), 5); 
    cout << "\nThe first element is: " << v[0]; 
  
    // Inserts 20 at the end 
    v.emplace_back(20); 
    n = v.size(); 
    cout << "\nThe last element is: " << v[n - 1]; 
  
    // erases the vector 
    v.clear(); 
    cout << "\nVector size after erase(): " << v.size(); 
  
    // two vector to perform swap 
    vector<int> v1, v2; 
    v1.push_back(1); 
    v1.push_back(2); 
    v2.push_back(3); 
    v2.push_back(4); 
  
    cout << "\n\nVector 1: "; 
    for (int i = 0; i < v1.size(); i++) 
        cout << v1[i] << " "; 
  
    cout << "\nVector 2: "; 
    for (int i = 0; i < v2.size(); i++) 
        cout << v2[i] << " "; 
  
    // Swaps v1 and v2 
    v1.swap(v2); 
  
    cout << "\nAfter Swap \nVector 1: "; 
    for (int i = 0; i < v1.size(); i++) 
        cout << v1[i] << " "; 
  
    cout << "\nVector 2: "; 
    for (int i = 0; i < v2.size(); i++) 
        cout << v2[i] << " "; 
} 

// Output:
The vector elements are: 10 10 10 10 10 
The last element is: 15
The vector elements are: 10 10 10 10 10 
The first element is: 5
The first element is: 10
The first element is: 5
The last element is: 20
Vector size after erase(): 0

Vector 1: 1 2 
Vector 2: 3 4 
After Swap 
Vector 1: 3 4 
Vector 2: 1 2
```

## Vector Example

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

// Pass by reference
void Print(vector< vector<int> > &inceptionvec)
    {
    cout << "Vector of vectors: " << endl;
    // Go through each row
    for(int i = 0; i < inceptionvec.size(); i++)
        {
        // Go through each column
        for(int j = 0; j < inceptionvec[i].size(); j++)
            {
            cout << inceptionvec[i][j] << " ";
            }
        cout << endl;
        }
    }

int main() 
    {
    cout << "\nC++ Vector Code" << endl;
    
    /* Vectors are a basic unit of data storage. Use it instead of array. */
    
    // Create a vector
    vector<int> myvec;
    
    // Add some numbers to the vector
    myvec.push_back(4);
    myvec.push_back(3);
    myvec.push_back(2);
    myvec.push_back(1);
    
	// Print the unsorted vector.
    cout << "Unsorted vector: " << endl;
    for(int i = 0; i < myvec.size(); i++) 
		{ 
		cout << myvec[i] << " "; 
		}
    cout << endl << endl;
	
    // Sort the vector using std's sort.
    std::sort(myvec.begin(), myvec.begin()+myvec.size());
    
    // Print the sorted vector.
    cout << "Sorted vector: " << endl;
    for(int i = 0; i < myvec.size(); i++) 
		{ 
		cout << myvec[i] << " "; 
		}
    cout << endl << endl;
    
    // Create a vector of vectors
    vector< vector<int> > inceptionvec;
    // Fill it up as a 3 by 3 table.
    int positionnumber = 0; // Fills our table up from 1 to 9.
    for(int i = 0; i < 3; i++) // Each row.
        {
        // Add a vector to our "vector that holds vectors". AKA, add a row to our "table".
        vector<int> row;
        inceptionvec.push_back(row);
		
		// For this new row, create + fill each "column" by adding to the row.
		// (The vector/row we just created is indexed at "i" in inceptionvec.)
        for(int j = 0; j < 3; j++) // Each column.
            {
            positionnumber += 1;
            
            // Add this particular spot in the table (which is [i][j] push the number we want.
            inceptionvec[i].push_back(positionnumber);
            }
        }
    
    // Print our vector of vectors (passed by reference to a function).
    Print(inceptionvec);
	
	return 0;
    }
    
// Output:

Unsorted vector: 
4 3 2 1 

Sorted vector: 
1 2 3 4 

Vector of vectors: 
1 2 3 
4 5 6 
7 8 9 
```

## How do vectors in C++ work?

Typically, vectors have to be declared first in any program which uses them. The usual syntax is as follows:

```cpp
vector <type> variable_name (no._of_elements);
```

The optional element in the syntax is the &lt;no. of elements&gt; portion, which can either be declared or not. The syntax would then be:

```cpp
vector <type> variable_name;
```

The above is an example of an empty vector which will have zero elements in it. To break down the syntax of a vector, the argument &lt;type&gt; is the data type that one would like to store in the vector. These can be an integer, double or string type depending on the value stored. The ‘variable name’ can be anything that the programmer chooses it to be. Some examples of vector code are as follows:

```cpp
vector <int> age (20);
vector <double> grades (20);
vector <string> names (20);
```

The above command line in C++ would create a vector with the name ‘age’, ‘grades’ and ‘names’. The type of value that the vector ‘age’ is allowed to store will be whole integers only, i.e. numbers without decimal places. Similarly, ‘grades’ will be able to store decimal values and ‘names’ will store in the form of strings. The size of the vector is specified by the number 20, i.e. it will allow for the storage of 20 values under the same variable ‘age’. So this is a classic example of declaring vectors in the programming language C++.

Individual elements in the vector can be referred with the use of square brackets after the vector has been declared in the following fashion:

```cpp
age [23];
```

However, simply declaring a vector in the program would not work until a directive called \#include is provided in the beginning of the program. This is because since vectors are a Standard Library facility, and not a built-in part of the core language. The example is as follows:

```cpp
#include <vector>
vector <int> age (20);
```

The above code would activate the vector and make it usable in the program. These were the basics of activating, declaring and referring to individual elements in a vector. A typical program which will allow the entry of student grades will look like the following:

```cpp
#include <iostream>
#include <vector>
using namespace std;
int main()
{
vector<double> student_marks(20);
for (vector<double>::size_type i = 0; i < 20; i++)
{
cout << “Enter marks for student #” << i+1
<< “: ” << flush;
cin >> student_marks[i];
}
// … Do some stuff with the values
return 0;
}
```

## Dynamic nature of vectors

As discussed earlier, that vectors are special given that they can be dynamic in nature i.e. they can be resized. Vectors can be resized during the program execution to include or even reduced in size.

In the example from the previous fragment above, if we don’t know ahead of time \(i.e., at the time we are writing the program\) that there are 20 students, we could obtain that information at run-time \(e.g., prompt the user for the number of students\) and resize the vector accordingly, as shown below \(though we notice that the example is somewhat silly, in that we could have waited until having the value of num\_students and then declare the vector initializing it with that size\):

```cpp
vector<double> student_marks;
// no size specified: vector contains
// no elements
int num_students;
cout << “Number of students: ” << flush;
cin >> num_students;
student_marks.resize (num_students);
for (vector<double>::size_type i = 0; i < num_students; i++)
{
cout << “Enter marks for student #” << i+1
<< “: ” << flush;
cin >> student_marks[i];
}
```

Notice that the valid subscripts for a vector with num\_students elements are 0 to num\_students−1. For that reason, the for loop starts at 0 and goes while i is less than num\_elements.

## Inserting and Removing Elements

Methods push\_back and pop\_back insert and remove \(respectively\) elements at the end of the vector. For situations where we need to insert or remove at an arbitrary position, we have methods remove and remove. We notice that these methods are inefficient with a vector \(they take linear time\` since all the remaining elements from the given position to the end have to be shifted\). However, for situations where we must support these operations, class vector does provide the facilities to do so.

Methods insert and remove use iterators \(discussed in the next section\) as parameters to indicate the position at which we want to insert or remove the element\(s\). However, a “quick and dirty” solution is available, given the nature of vector iterators \(they support operations essentially identical to pointer arithmetic\).  The code sample below illustrates these features:

```cpp
#include <vector>
using namespace std;
int main()
{
vector<double> values(10);
// Create vector with 10 elements (initialized to 0.0)
values.insert (values.begin() + 5, 1.4142);
// Insert sqr root of 2 at position 5 (before the element that was at position 5)
values.remove (values.begin() + 3);
// Remove element at position 3
```

In the sample above, the expressions values.begin\(\) + n work similarly to the idea of getting a pointer to element n of an array – we get a pointer to the first element of the array, then add an integer offset to obtain a pointer pointing n elements after the beginning of the array.  The expression values.begin\(\) returns an iterator pointing to the first element of the vector, and adding an integer value n results in an iterator pointing n positions after the first element, providing the required parameter for insert and remove methods.  


## All Vector Functions

* [vector::begin\(\) and vector::end\(\)](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/)
* [vector rbegin\(\) and rend\(\)](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/)
* [vector::cbegin\(\) and vector::cend\(\)](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/)
* [vector::crend\(\) and vector::crbegin\(\)](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/)
* [vector::assign\(\)](https://www.geeksforgeeks.org/vector-assign-in-c-stl/)
* [vector::at\(\)](https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/)
* [vector::back\(\)](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/)
* [vector::capacity\(\)](https://www.geeksforgeeks.org/vector-capacity-function-in-c-stl/)
* [vector::clear\(\)](https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/)
* [vector::push\_back\(\)](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/)
* [vector::pop\_back\(\)](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/)
* [vector::empty\(\)](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/)
* [vector::erase\(\)](https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/)
* [vector::size\(\)](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/)
* [vector::swap\(\)](https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/)
* [vector::reserve\(\)](https://www.geeksforgeeks.org/using-stdvectorreserve-whenever-possible/)
* [vector::resize\(\)](https://www.geeksforgeeks.org/vector-resize-c-stl/)
* [vector::shrink\_to\_fit\(\)](https://www.geeksforgeeks.org/vector-shrink_to_fit-function-in-c-stl/)
* [vector::operator=](https://www.geeksforgeeks.org/vectoroperator-vectoroperator-c-stl/)
* [vector::operator\[\]](https://www.geeksforgeeks.org/vectoroperator-vectoroperator-c-stl/)
* [vector::front\(\)](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/)
* [vector::data\(\)](https://www.geeksforgeeks.org/vector-data-function-in-c-stl/)
* [vector::emplace\_back\(\)](https://www.geeksforgeeks.org/vectoremplace_back-c-stl/)
* [vector::emplace\(\)](https://www.geeksforgeeks.org/vector-emplace-function-in-c-stl/)
* [vector::max\_size\(\)](https://www.geeksforgeeks.org/vector-max_size-function-in-c-stl/)
* [vector::insert\(\)](https://www.geeksforgeeks.org/vector-insert-function-in-c-stl/)

