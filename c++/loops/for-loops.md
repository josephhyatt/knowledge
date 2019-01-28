# For Loops

## C++ for Loop Syntax

```cpp
for(initializationStatement; testExpression; updateStatement) {
    // codes 
}
```

where, only testExpression is mandatory.

## How for loop works?

1. The initialization statement is executed only once at the beginning.
2. Then, the test expression is evaluated.
3. If the test expression is false, for loop is terminated. But if the test expression is true, codes inside body of `for` loop is executed and update expression is updated.
4. Again, the test expression is evaluated and this process repeats until the test expression is false.

## Flowchart of for Loop in C++

![Flowchart of for loop in C++ Programming](https://cdn.programiz.com/sites/tutorial2program/files/for-loop.jpg)

## Example 1: C++ for Loop

```cpp
// C++ Program to find factorial of a number
// Factorial on n = 1*2*3*...*n

#include <iostream>
using namespace std;

int main() 
{
    int i, n, factorial = 1;

    cout << "Enter a positive integer: ";
    cin >> n;

    for (i = 1; i <= n; ++i) {
        factorial *= i;   // factorial = factorial * i;
    }

    cout<< "Factorial of "<<n<<" = "<<factorial;
    return 0;
}
```

**Output**

```cpp
Enter a positive integer: 5
Factorial of 5 = 120
```

In the program, user is asked to enter a positive integer which is stored in variable n\(suppose user entered 5\). Here is the working of `for` loop:

1. Initially, i is equal to 1, test expression is true, factorial becomes 1.
2. i is updated to 2, test expression is true, factorial becomes 2.
3. i is updated to 3, test expression is true, factorial becomes 6.
4. i is updated to 4, test expression is true, factorial becomes 24.
5. i is updated to 5, test expression is true, factorial becomes 120.
6. i is updated to 6, test expression is false, `for` loop is terminated.

In the above program, variable i is not used outside of the `for` loop. In such cases, it is better to declare the variable in for loop \(at initialization statement\).

```cpp
#include <iostream>
using namespace std;

int main() 
{
    int n, factorial = 1;

    cout << "Enter a positive integer: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        factorial *= i;   // factorial = factorial * i;
    }

    cout<< "Factorial of "<<n<<" = "<<factorial;
    return 0;
}
```

Check out these examples to learn more:

* [C++ Program to Calculate Sum of Natural Numbers](https://www.programiz.com/cpp-programming/examples/sum-natural-number)
* [C++ Program to Find Factorial](https://www.programiz.com/cpp-programming/examples/factorial)
* [C++ Program to Generate Multiplication Table](https://www.programiz.com/cpp-programming/examples/multiplication-table)

