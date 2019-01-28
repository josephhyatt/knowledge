# While Loops

## C++ While Loop Syntax

```cpp
while (testExpression) 
{
     // codes  
}
```

where, testExpression is checked on each entry of the while loop.

## How while loop works?

* The while loop evaluates the test expression.
* If the test expression is true, codes inside the body of while loop is evaluated.
* Then, the test expression is evaluated again. This process goes on until the test expression is false.
* When the test expression is false, while loop is terminated.

## Flowchart of while Loop

![Flowchart of while loop in C++ Programming](https://cdn.programiz.com/sites/tutorial2program/files/while-loop_0.jpg)

## Example 1: C++ while Loop

```cpp
// C++ Program to compute factorial of a number
// Factorial of n = 1*2*3...*n

#include <iostream>
using namespace std;

int main() 
{
    int number, i = 1, factorial = 1;

    cout << "Enter a positive integer: ";
    cin >> number;
    
    while ( i <= number) {
        factorial *= i;      //factorial = factorial * i;
        ++i;
    }

    cout<<"Factorial of "<< number <<" = "<< factorial;
    return 0;
}
```

**Output**

```cpp
Enter a positive integer: 4
Factorial of 4 = 24
```

In this program, user is asked to enter a positive integer which is stored in variable number. Let's suppose, user entered 4.

Then, the while loop starts executing the code. Here's how while loop works:

1. Initially, `i = 1`, test expression `i <= number` is true and factorial becomes 1.
2. Variable i is updated to 2, test expression is `true`, factorial becomes 2.
3. Variable i is updated to 3, test expression is `true`, factorial becomes 6.
4. Variable i is updated to 4, test expression is `true`, factorial becomes 24.
5. Variable i is updated to 5, test expression is `false` and while loop is terminated.

