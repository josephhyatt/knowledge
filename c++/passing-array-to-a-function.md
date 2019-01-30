# Passing Array to a Function

[Arrays](https://www.programiz.com/cpp-programming/arrays) can be passed to a [function](https://www.programiz.com/cpp-programming/function) as an argument. Consider this example to pass one-dimensional array to a function:

## Example 1: Passing One-dimensional Array to a Function

**C++ Program to display marks of 5 students by passing one-dimensional array to a function.**

```cpp
#include <iostream>
using namespace std;

void display(int marks[5]);

int main()
{
    int marks[5] = {88, 76, 90, 61, 69};
    display(marks);
    return 0;
}

void display(int m[5])
{
    cout << "Displaying marks: "<< endl;

    for (int i = 0; i < 5; ++i)
    {
        cout << "Student "<< i + 1 <<": "<< m[i] << endl;
    }
}
```

**Output**

```cpp
Displaying marks: 
Student 1: 88
Student 2: 76
Student 3: 90
Student 4: 61
Student 5: 69
```

When an array is passed as an argument to a function, only the name of an array is used as argument.

```cpp
display(marks);
```

Also notice the difference while passing array as an argument rather than a variable.

```cpp
void display(int m[5]);
```

The argument `marks` in the above code represents the memory address of first element of array `marks[5]`.

And the formal argument `int m[5]` in function declaration converts to `int* m;`. This pointer points to the same address pointed by the array marks.

That's the reason, although the function is manipulated in the user-defined function with different array name `m[5]`, the original array marks is manipulated.

C++ handles passing an array to a function in this way to save memory and time.

## Passing Multidimensional Array to a Function

[Multidimensional array](https://www.programiz.com/cpp-programming/multidimensional-arrays) can be passed in similar way as one-dimensional array. Consider this example to pass two dimensional array to a function:

## Example 2: Passing Multidimensional Array to a Function

**C++ Program to display the elements of two dimensional array by passing it to a function.**

```cpp
#include <iostream>
using namespace std;

void display(int n[3][2]);

int main()
{
    int num[3][2] = {
        {3, 4},
        {9, 5},
        {7, 1}

    };
    display(num);

    return 0;
}

void display(int n[3][2])
{

    cout << "Displaying Values: " << endl;
    for(int i = 0;  i < 3; ++i)
    {
        for(int j = 0; j < 2; ++j)
        {
            cout << n[i][j] << " ";
        }
    }
}
```

**Output**

```cpp
Displaying Values: 
3 4 9 5 7 1 
```

In the above program, the multi-dimensional array num is passed to the function `display()`.

Inside, `display()` function, the array n \(num\) is traversed using a nested for loop.

The program uses 2 [for loops](https://www.programiz.com/cpp-programming/for-loop) to iterate over the elements inside a 2-dimensional array. If it were a 3-dimensional array, you should use 3 for loops.

Finally, all elements are printed onto the screen.

**Note:** Multidimensional array with dimension more than 2 can be passed in similar way as two dimensional array.

Check out these examples to learn more:

* [C++ Program to Multiply two Matrices by Passing Matrix to Function](https://www.programiz.com/cpp-programming/examples/matrix-multiplication-function)

