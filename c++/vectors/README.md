# Vectors

## What are Vectors in C++?

In the computer programming languages, arrays are used to store sequential data which are of static nature. Generally, arrays are non-dynamic, that is to say, they are of fixed size, however, C++ also allows us to store data in dynamic arrays which are known as vectors in C++.

[Vectors](https://www.toppr.com/bytes/vectors/) are unique in their characteristics as they can be re-seized by the programmer depending on the need of the task to be executed. This is not a typical characteristic of fixed-sized arrays where only a given number of values can be stored under a single variable name.

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


