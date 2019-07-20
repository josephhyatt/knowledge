# Do While Loops

## C++ do...while Loop Syntax

The do...while loop is a variant of the while loop with one important difference. The body of do...while loop is executed once before the test expression is checked.

The syntax of do..while loop is:

```cpp
do {
   // codes;
}
while (testExpression);
```

## How do...while loop works?

* The codes inside the body of loop is executed at least once. Then, only the test expression is checked.
* If the test expression is true, the body of loop is executed. This process continues until the test expression becomes false.
* When the test expression is false, do...while loop is terminated.

## Flowchart of do...while Loop

![Flowchart of do while loop in C++ programming](https://cdn.programiz.com/sites/tutorial2program/files/do-while-loop.jpg)

## Example 1: C++ do...while Loop

```cpp
// C++ program to add numbers until user enters 0

#include <iostream>
using namespace std;

int main() 
{
    float number, sum = 0.0;
    
    do {
        cout<<"Enter a number: ";
        cin>>number;
        sum += number;
    }
    while(number != 0.0);

    cout<<"Total sum = "<<sum;
    
    return 0;
}
```

**Output**

```cpp
Enter a number: 2
Enter a number: 3
Enter a number: 4
Enter a number: -4
Enter a number: 2
Enter a number: 4.4
Enter a number: 2
Enter a number: 0
```

