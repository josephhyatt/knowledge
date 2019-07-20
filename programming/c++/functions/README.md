# Functions

In programming, function refers to a segment that groups code to perform a specific task.

Depending on whether a function is predefined or created by programmer; there are two types of function:

1. Library Function
2. User-defined Function

## Library Function

Library functions are the built-in function in C++ programming.

Programmer can use library function by invoking function directly; they don't need to write it themselves.

## Example 1: Library Function

```cpp
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    double number, squareRoot;
    cout << "Enter a number: ";
    cin >> number;

    // sqrt() is a library function to calculate square root
    squareRoot = sqrt(number);
    cout << "Square root of " << number << " = " << squareRoot;
    return 0;
}
```

**Output**

```cpp
Enter a number: 26
Square root of 26 = 5.09902
```

In the example above, `sqrt()` library function is invoked to calculate the square root of a number.

Notice code `#include <cmath>` in the above program. Here, `cmath` is a header file. The function definition of `sqrt()`\(body of that function\) is present in the cmath header file.

You can use all functions defined in `cmath` when you include the content of file `cmath` in this program using `#include <cmath>` .

Every valid C++ program has at least one function, that is, `main()` function.

## User-defined Function

C++ allows programmer to define their own function.

A user-defined function groups code to perform a specific task and that group of code is given a name\(identifier\).

When the function is invoked from any part of program, it all executes the codes defined in the body of function.

#### How user-defined function works in C Programming?

![Working of function in C++ programming](https://cdn.programiz.com/sites/tutorial2program/files/function.jpg)

Consider the figure above.

When a program begins running, the system calls the `main()` function, that is, the system starts executing codes from `main()` function.

When control of the program reaches to `function_name()` inside `main()`, it moves to `void function_name()` and all codes inside `void function_name()` is executed.

Then, control of the program moves back to the main function where the code after the call to the `function_name()` is executed as shown in figure above.

## Example 2: User Defined Function

**C++ program to add two integers. Make a function `add()` to add integers and display sum in main\(\) function.**

```cpp
#include <iostream>
using namespace std;

// Function prototype (declaration)
int add(int, int);

int main()
{
    int num1, num2, sum;
    cout<<"Enters two numbers to add: ";
    cin >> num1 >> num2;

    // Function call
    sum = add(num1, num2);
    cout << "Sum = " << sum;
    return 0;
}

// Function definition
int add(int a, int b)
{
    int add;
    add = a + b;

    // Return statement
    return add;
}
```

**Output**

```cpp
Enters two integers: 8
-4
Sum = 4
```

## Function prototype \(declaration\)

If a user-defined function is defined after `main()` function, compiler will show error. It is because compiler is unaware of user-defined function, types of argument passed to function and return type.

In C++, function prototype is a declaration of function without its body to give compiler information about user-defined function. Function prototype in the above example is:

```cpp
int add(int, int);
```

You can see that, there is no body of function in prototype. Also, there are only return type of arguments but no arguments. You can also declare function prototype as below but it's not necessary to write arguments.

```cpp
int add(int a, int b);
```

**Note:** It is not necessary to define prototype if user-defined function exists before `main()`function.

## Function Call

To execute the codes of function body, the user-defined function needs to be invoked\(called\).

In the above program, `add(num1,num2);` inside `main()` function calls the user-defined function.

The function returns an integer which is stored in variable add.

## Function Definition

The function itself is referred as function definition. Function definition in the above program is:

```cpp
// Function definition
int add(int a,int b)
{
    int add;
    add = a + b;
    return add;
}
```

When the function is called, control is transferred to the first statement of the function body.

Then, other statements in function body are executed sequentially.

When all codes inside function definition is executed, control of program moves to the calling program.

## Passing Arguments to Function

In programming, argument \(parameter\) refers to the data which is passed to a function \(function definition\) while calling it.

In the above example, two variables, num1 and num2 are passed to function during function call. These arguments are known as actual arguments.

The value of num1 and num2 are initialized to variables a and b respectively. These arguments a and b are called formal arguments.

This is demonstrated in figure below:

![Passing argument to a function in C++ programming](https://cdn.programiz.com/sites/tutorial2program/files/passing-arguments-cpp.jpg)

**Notes on passing arguments**

* The numbers of actual arguments and formals argument should be the same. \(Exception: [Function Overloading](https://www.programiz.com/cpp-programming/function-overloading)\)
* The type of first actual argument should match the type of first formal argument. Similarly, type of second actual argument should match the type of second formal argument and so on.
* You may call function a without passing any argument. The number\(s\) of argument passed to a function depends on how programmer want to solve the problem.
* You may assign default values to the argument. These arguments are known as [default arguments](https://www.programiz.com/cpp-programming/default-argument).
* In the above program, both arguments are of `int` type. But it's not necessary to have both arguments of same type.

## Return Statement

A function can return a single value to the calling program using return statement.

In the above program, the value of add is returned from user-defined function to the calling program using statement below:

```cpp
return add;
```

The figure below demonstrates the working of return statement.

![Returning value from a function in C++ programming.](https://cdn.programiz.com/sites/tutorial2program/files/return-value-cpp_0.jpg)

In the above program, the value of add inside user-defined function is returned to the calling function. The value is then stored to a variable sum.

Notice that the variable returned, i.e., add is of type `int` and sum is also of int type.

Also, notice that the return type of a function is defined in function declarator `int add(int a, int b)`. The `int` before `add(int a, int b)` means the function should return a value of type `int`.

If no value is returned to the calling function then, `void` should be used.

## Example 3: Prime Numbers Between two Intervals

```cpp
#include <iostream>
using namespace std;

int checkPrimeNumber(int);

int main()
{
    int n1, n2;
    bool flag;

    cout << "Enter two positive integers: ";
    cin >> n1 >> n2;

    cout << "Prime numbers between " << n1 << " and " << n2 << " are: ";

    for(int i = n1+1; i < n2; ++i)
    {
        // If i is a prime number, flag will be equal to 1
        flag = checkPrimeNumber(i);

        if(flag)
            cout << i << " ";
    }
    return 0;
}

// user-defined function to check prime number
int checkPrimeNumber(int n)
{
    bool flag = true;

    for(int j = 2; j <= n/2; ++j)
    {
        if (n%j == 0)
        {
            flag = false;
            break;
        }
    }
    return flag;
}
```

**Output**

```cpp
Enter two positive integers: 12
55
Prime numbers between 12 and 55 are: 13 17 19 23 29 31 37 41 43 47 53 
```

To print all prime numbers between two integers, `checkPrimeNumber()` function is created. This function [checks whether a number is prime or not](https://www.programiz.com/cpp-programming/examples/prime-number).

All integers between n1 and n2 are passed to this function.

If a number passed to `checkPrimeNumber()` is a prime number, this function returns true, if not the function returns false.

If the user enters larger number first, this program will not work as intended. To solve this issue, you need to [swap numbers](https://www.programiz.com/cpp-programming/examples/swapping) first.

## Example 4: Check Prime Number

```cpp
#include <iostream>
using namespace std;

int checkPrimeNumber(int);

int main()
{
  int n;

  cout << "Enter a positive  integer: ";
  cin >> n;
  
  if(checkPrimeNumber(n) == 0)
    cout << n << " is a prime number.";
  else
    cout << n << " is not a prime number.";
  return 0;
}
int checkPrimeNumber(int n)
{
  bool flag = false;

  for(int i = 2; i <= n/2; ++i)
  {
      if(n%i == 0)
      {
          flag = true;
          break;
      }
  }
  return flag;
}

```

**Output**

```cpp
Enter a positive  integer: 23
23 is a prime number.
```

In this example, the number entered by the user is passed to the `checkPrimeNumber()` function.

This function returns `true` if the number passed to the function is a prime number, and returns `false` if the number passed is not a prime number.

Finally, the appropriate message is printed from the `main()` function



## Example 5: Check Whether a Number can be Expressed as a Sum of Two Prime Numbers

```cpp
#include <iostream>
using namespace std;

bool checkPrime(int n);

int main()
{
    int n, i;
    bool flag = false;

    cout << "Enter a positive  integer: ";
    cin >> n;

    for(i = 2; i <= n/2; ++i)
    {
        if (checkPrime(i))
        {
            if (checkPrime(n - i))
            {
                cout << n << " = " << i << " + " << n-i << endl;
                flag = true;
            }
        }
    }

    if (!flag)
      cout << n << " can't be expressed as sum of two prime numbers.";

    return 0;
}

// Check prime number
bool checkPrime(int n)
{
    int i;
    bool isPrime = true;

    for(i = 2; i <= n/2; ++i)
    {
        if(n % i == 0)
        {
            isPrime = false;
            break;
        }
    }

    return isPrime;
}
```

**Output**

```cpp
Enter a positive integer: 34
34 = 3 + 31
34 = 5 + 29
34 = 11 + 23
34 = 17 + 17
```

