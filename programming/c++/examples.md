# Examples

## Store Information in Structure and Display it

In this program, a structure, student is created. This structure has three members: name \(string\), roll \(integer\) and marks \(float\). Then, we created a structure array of size 10 to store information of 10 students. Using [for loop](https://www.programiz.com/cpp-programming/for-loop), the program takes the information of 10 students from the user and displays it on the screen.

```cpp
#include <iostream>

using namespace std;

struct student
{
    char name[50];
    int roll;
    float marks;
} s[10];

int main()
{
    cout << "Enter information of students: " << endl;

    // storing information
    for(int i = 0; i < 10; ++i)
    {
        s[i].roll = i+1;
        cout << "For roll number" << s[i].roll << "," << endl;

        cout << "Enter name: ";
        cin >> s[i].name;

        cout << "Enter marks: ";
        cin >> s[i].marks;

        cout << endl;
    }

    cout << "Displaying Information: " << endl;

    // Displaying information
    for(int i = 0; i < 10; ++i)
    {
        cout << "\nRoll number: " << i+1 << endl;
        cout << "Name: " << s[i].name << endl;
        cout << "Marks: " << s[i].marks << endl;
    }

    return 0;
}

```

**Output**

```cpp
Enter information of students: 

For roll number1,
Enter name: Tom
Enter marks: 98

For roll number2,
Enter name: Jerry
Enter marks: 89
.
.
.
Displaying Information:

Roll number: 1
Name: Tom
Marks: 98
.
.
.
```

## Calculate Difference Between Two Time Period

```cpp
// Computes time difference of two time period
// Time periods are entered by the user
#include <iostream>

using namespace std;

struct TIME
{
  int seconds;
  int minutes;
  int hours;
};

void computeTimeDifference(struct TIME, struct TIME, struct TIME *);

int main()
{
    struct TIME t1, t2, difference;

    cout << "Enter start time." << endl;
    cout << "Enter hours, minutes and seconds respectively: ";
    cin >> t1.hours >> t1.minutes >> t1.seconds;

    cout << "Enter stop time." << endl;
    cout << "Enter hours, minutes and seconds respectively: ";
    cin >> t2.hours >> t2.minutes >> t2.seconds;

    computeTimeDifference(t1, t2, &difference);

    cout << endl << "TIME DIFFERENCE: " << t1.hours << ":" << t1.minutes << ":" << t1.seconds;
    cout << " - " << t2.hours << ":" << t2.minutes << ":" << t2.seconds;
    cout << " = " << difference.hours << ":" << difference.minutes << ":" << difference.seconds;
    return 0;
}
void computeTimeDifference(struct TIME t1, struct TIME t2, struct TIME *difference){
    
    if(t2.seconds > t1.seconds)
    {
        --t1.minutes;
        t1.seconds += 60;
    }

    difference->seconds = t1.seconds - t2.seconds;
    if(t2.minutes > t1.minutes)
    {
        --t1.hours;
        t1.minutes += 60;
    }
    difference->minutes = t1.minutes-t2.minutes;
    difference->hours = t1.hours-t2.hours;
}
```

**Output**

```cpp
Enter hours, minutes and seconds respectively: 11
33
52
Enter stop time.
Enter hours, minutes and seconds respectively: 8
12
15

TIME DIFFERENCE: 11:33:52 - 8:12:15 = 3:21:37
```

In this program, user is asked to enter two time periods and these two periods are stored in structure variables t1 and t2 respectively.

Then, the `computeTimeDifference()` function calculates the difference between the time periods and the result is displayed on the screen from the `main()` function without returning it \(call by reference\).

## Add Complex Numbers by Passing Structure to a Function

```cpp
// Complex numbers are entered by the user
#include <iostream>

using namespace std;

typedef struct complex
{
    float real;
    float imag;
} complexNumber;

complexNumber addComplexNumbers(complex, complex);

int main()
{
    complexNumber n1, n2, temporaryNumber;
    char signOfImag;

    cout << "For 1st complex number," << endl;
    cout << "Enter real and imaginary parts respectively:" << endl;
    cin >> n1.real >> n1.imag;

    cout << endl << "For 2nd complex number," << endl;
    cout << "Enter real and imaginary parts respectively:" << endl;
    cin >> n2.real >> n2.imag;

    signOfImag = (temporaryNumber.imag > 0) ? '+' : '-';
    temporaryNumber.imag = (temporaryNumber.imag > 0) ? temporaryNumber.imag : -temporaryNumber.imag; 

    temporaryNumber = addComplexNumbers(n1, n2);    
    cout << "Sum = "  << temporaryNumber.real << temporaryNumber.imag << "i";
    return 0;
}

complexNumber addComplexNumbers(complex n1,complex n2)
{
      complex temp;
      temp.real = n1.real+n2.real;
      temp.imag = n1.imag+n2.imag;
      return(temp);
}
```

**Output**

```cpp
Enter real and imaginary parts respectively:
3.4
5.5

For 2nd complex number,
Enter real and imaginary parts respectively:
-4.5
-9.5
Sum = -1.1-4i
```

In the problem, two complex numbers entered by the user is stored in structures n1 and n2. These two structures are passed to `addComplexNumbers()` function which calculates the sum and returns the result to the `main()` function. Finally, the sum is displayed from the `main()` function.

## Add Two Distances \(in inch-feet\) System Using Structures

```cpp
#include <iostream>

using namespace std;

struct Distance{
    int feet;
    float inch;
}d1 , d2, sum;

int main()
{
    cout << "Enter 1st distance," << endl;
    cout << "Enter feet: ";
    cin >> d1.feet;
    cout << "Enter inch: ";
    cin >> d1.inch;

    cout << "\nEnter information for 2nd distance" << endl;
    cout << "Enter feet: ";
    cin >> d2.feet;
    cout << "Enter inch: ";
    cin >> d2.inch;

    sum.feet = d1.feet+d2.feet;
    sum.inch = d1.inch+d2.inch;

    // changing to feet if inch is greater than 12
    if(sum.inch > 12)
    {
        ++ sum.feet;
        sum.inch -= 12;
    } 

    cout << endl << "Sum of distances = " << sum.feet << " feet  " << sum.inch << " inches";
    return 0;
}
```

**Output**

```cpp
Enter 1st distance,
Enter feet: 6
Enter inch: 3.4

Enter information for 2nd distance
Enter feet: 5
Enter inch: 10.2

Sum of distances = 12 feet  1.6 inches
```

In this program, a structure `Distance` containing two data members \(inch and feet\) is declared to store the distance in inch-feet system. Here, two structure variables d1 and d2 are created to store the distance entered by the user. And, the sum variables stores the sum of the distances. The `if..else` statement is used to convert inches to feet if the value of inch of sum variable is greater than 12.

## Store Information of a Student in a Structure

In this program, a structure\(student\) is created which contains name, roll and marks as its data member. Then, a structure variable\(s\) is created. Then, data \(name, roll and marks\) is taken from user and stored in data members of structure variable `s`. Finally, the data entered by user is displayed.

```cpp
#include <iostream>

using namespace std;

struct student
{
    char name[50];
    int roll;
    float marks;
};

int main() 
{
    student s;
    cout << "Enter information," << endl;
    cout << "Enter name: ";
    cin >> s.name;
    cout << "Enter roll number: ";
    cin >> s.roll;
    cout << "Enter marks: ";
    cin >> s.marks;

    cout << "\nDisplaying Information," << endl;
    cout << "Name: " << s.name << endl;
    cout << "Roll: " << s.roll << endl;
    cout << "Marks: " << s.marks << endl;
    return 0;
}
```

**Output**

```cpp
Enter information,
Enter name: Bill
Enter roll number: 4
Enter marks: 55.6

Displaying Information,
Name: Bill
Roll: 4
Marks: 55.6
```

In this program, student \(structure\) is created. This structure has three members: name \(string\), roll \(integer\) and marks \(float\). Then, a structure variable s is created to store information and display it on the screen.

## Sort Elements in Lexicographical Order \(Dictionary Order\)

This program takes 10 words from the user and sort them in lexicographical order.

```cpp
#include <iostream>

using namespace std;

int main()
{
    string str[10], temp;

    cout << "Enter 10 words: " << endl;
    for(int i = 0; i < 10; ++i)
    {
      getline(cin, str[i]);
    }

    for(int i = 0; i < 9; ++i)
       for( int j = i+1; j < 10; ++j)
       {
          if(str[i] > str[j])
          {
            temp = str[i];
            str[i] = str[j];
            str[j] = temp;
          }
    }

    cout << "In lexicographical order: " << endl;

    for(int i = 0; i < 10; ++i)
    {
       cout << str[i] << endl;
    }
    return 0;
}
```

**Output**

```cpp
Enter 10 words: 
C 
C++
Java
Python
Perl
R
Matlab
Ruby
JavaScript
PHP
In lexicographical order: 
C
C++
Java
JavaScript
Matlab
PHP
Perl
Python
R
Ruby
```

To solve this program, an array of string object str\[10\] is created. The 10 words entered by the user is stored in this array. Then, the array is sorted in lexicographical order using nested for loop and displayed on the screen.

## Copy String Object

```cpp
#include <iostream>

using namespace std;

int main()
{
    string s1, s2;

    cout << "Enter string s1: ";
    getline (cin, s1);

    s2 = s1;

    cout << "s1 = "<< s1 << endl;
    cout << "s2 = "<< s2;

    return 0;
}
```

**Output**

```cpp
Enter string s1: C++ Strings
s1 = C++ Strings
s2 = C++ Strings
```

To copy c-strings in C++, `strcpy()` function is used.

### Example 1: Copy C-Strings

```cpp
#include <iostream>
#include <cstring>

using namespace std;

int main()
{
    char s1[100], s2[100];

    cout << "Enter string s1: ";
    cin.getline(s1, 100);

    strcpy(s2, s1);

    cout << "s1 = "<< s1 << endl;
    cout << "s2 = "<< s2;

    return 0;
}
```

**Output**

```cpp
Enter string s1: C-Strings
s1 = C-Strings
s2 = C-Strings
```

## Concatenate Two Strings

You can concatenate two string objects in C++ using **+** operator.

### Example 1: Concatenate String Objects

```cpp
#include <iostream>

using namespace std;

int main()
{
    string s1, s2, result;

    cout << "Enter string s1: ";
    getline (cin, s1);

    cout << "Enter string s2: ";
    getline (cin, s2);

    result = s1 + s2;

    cout << "Resultant String = "<< result;

    return 0;
}
```

**Output**

```cpp
Enter string s1: C++ Programming
Enter string s2:  is awesome.
Resultant String = C++ Programming is awesome.
```

You can concatenate two C-style strings in C++ using `strcat()` function.

### Example 2: Concatenate C-style Strings

```cpp
#include <iostream>
#include <cstring>

using namespace std;

int main()
{
    char s1[50], s2[50], result[100];

    cout << "Enter string s1: ";
    cin.getline(s1, 50);

    cout << "Enter string s2: ";
    cin.getline(s2, 50);

    strcat(s1, s2); 

    cout << "s1 = " << s1 << endl;
    cout << "s2 = " << s2;

    return 0;
}
```

**Output**

```cpp
Enter string s1: I love        
Enter string s2:  C++ programming 
s1 = I love C++ programming
s2 =  C++ programming
```

## Find the Length of a String

You can get the length of a string object by using a `size()` function or a `length()` function.

The `size()` and `length()` functions are just synonyms and they both do exactly same thing.

### Length of String Object

```cpp
#include <iostream>

using namespace std;

int main()
{
    string str = "C++ Programming";

    // you can also use str.length()
    cout << "String Length = " << str.size();

    return 0;
}
```

**Output**

```cpp
String Length = 15
```

### Length of C-style string

To get the length of a C-string string, `strlen()` function is used.

```cpp
#include <iostream>
#include <cstring>

using namespace std;

int main()
{
    char str[] = "C++ Programming is awesome";

    // you can also use str.length()
    cout << "String Length = " << strlen(str);

    return 0;
}
```

**Output**

```text
String Length = 26
```

## Remove all Characters in a String Except Alphabets

### Remove all characters except alphabets

This program takes a string \(object\) input from the user and removes all characters except alphabets.

```cpp
#include <iostream>

using namespace std;

int main() {
    string line;
    cout << "Enter a string: ";
    getline(cin, line);

    for(int i = 0; i < line.size(); ++i)
    {
        if (!((line[i] >= 'a' && line[i]<='z') || (line[i] >= 'A' && line[i]<='Z')))
        {
            line[i] = '\0';
        }
    }
    cout << "Output String: " << line;    
    return 0;
}
```

**Output**

```cpp
Enter a string: p2'r"o@gram84iz./
Output String: programiz
```

### Remove all characters except alphabets

This program below takes a string \(C-style string\) input from the user and removes all characters except alphabets.

```cpp
#include <iostream>

using namespace std;

int main() {
    char line[100], alphabetString[100];
    int j = 0;
    cout << "Enter a string: ";
    cin.getline(line, 100);

    for(int i = 0; line[i] != '\0'; ++i)
    {
        if ((line[i] >= 'a' && line[i]<='z') || (line[i] >= 'A' && line[i]<='Z'))
        {
            alphabetString[j++] = line[i]; 

        }
    }
    alphabetString[j] = '\0';

    cout << "Output String: " << alphabetString;    
    return 0;
}
```

**Output**

```cpp
Enter a string: P2'r"o@gram84iz./
Output String: Programiz
```

## Find the Number of Vowels, Consonants, Digits and White Spaces in a String

### From a C-style string

This program takes a C-style string from the user and calculates the number of vowels, consonants, digits and white-spaces.

```cpp
#include <iostream>
using namespace std;

int main()
{
    char line[150];
    int vowels, consonants, digits, spaces;

    vowels =  consonants = digits = spaces = 0;

    cout << "Enter a line of string: ";
    cin.getline(line, 150);
    for(int i = 0; line[i]!='\0'; ++i)
    {
        if(line[i]=='a' || line[i]=='e' || line[i]=='i' ||
           line[i]=='o' || line[i]=='u' || line[i]=='A' ||
           line[i]=='E' || line[i]=='I' || line[i]=='O' ||
           line[i]=='U')
        {
            ++vowels;
        }
        else if((line[i]>='a'&& line[i]<='z') || (line[i]>='A'&& line[i]<='Z'))
        {
            ++consonants;
        }
        else if(line[i]>='0' && line[i]<='9')
        {
            ++digits;
        }
        else if (line[i]==' ')
        {
            ++spaces;
        }
    }

    cout << "Vowels: " << vowels << endl;
    cout << "Consonants: " << consonants << endl;
    cout << "Digits: " << digits << endl;
    cout << "White spaces: " << spaces << endl;

    return 0;
}
```

**Output**

```cpp
Enter a line of string: This is 1 hell of a book.
Vowels: 7
Consonants: 10
Digits: 1
White spaces: 6
```

### From a String Object

This program takes a string object from the user and calculates the number of vowels, consonants, digits and white-spaces.

```cpp
#include <iostream>
using namespace std;

int main()
{
    string line;
    int vowels, consonants, digits, spaces;

    vowels =  consonants = digits = spaces = 0;

    cout << "Enter a line of string: ";
    getline(cin, line);

    for(int i = 0; i < line.length(); ++i)
    {
        if(line[i]=='a' || line[i]=='e' || line[i]=='i' ||
           line[i]=='o' || line[i]=='u' || line[i]=='A' ||
           line[i]=='E' || line[i]=='I' || line[i]=='O' ||
           line[i]=='U')
        {
            ++vowels;
        }
        else if((line[i]>='a'&& line[i]<='z') || (line[i]>='A'&& line[i]<='Z'))
        {
            ++consonants;
        }
        else if(line[i]>='0' && line[i]<='9')
        {
            ++digits;
        }
        else if (line[i]==' ')
        {
            ++spaces;
        }
    }

    cout << "Vowels: " << vowels << endl;
    cout << "Consonants: " << consonants << endl;
    cout << "Digits: " << digits << endl;
    cout << "White spaces: " << spaces << endl;

    return 0;
}
```

**Output**

```cpp
Enter a line of string: I have 2 C++ programming books.
Vowels: 8
Consonants: 14
Digits: 1
White spaces: 5
```

## Find the Frequency of Characters in a String

In this example, frequency of characters in a string object is computed. To do this, `size()` function is used to find the length of a string object. Then, the for loop is iterated until the end of the string. In each iteration, occurrence of character is checked and if found, the value of count is incremented by 1.

### Find Frequency of Characters of a String Object

```cpp
#include <iostream>
using namespace std;

int main()
{
    string str = "C++ Programming is awesome";
    char checkCharacter = 'a';
    int count = 0;

    for (int i = 0; i < str.size(); i++)
    {
        if (str[i] ==  checkCharacter)
        {
            ++ count;
        }
    }

    cout << "Number of " << checkCharacter << " = " << count;

    return 0;
}
```

**Output**

```cpp
Number of a = 2
```

In the example below, loop is iterated until the null character **'\0'** is encountered. Null character indicates the end of the string.

In each iteration, the occurrence of the character is checked.

### Find Frequency of Characters in a C-style String

```cpp
#include <iostream>

using namespace std;
int main()
{
   char c[] = "C++ programming is not easy.", check = 'm';
   int count = 0;

   for(int i = 0; c[i] != '\0'; ++i)
   {
       if(check == c[i])
           ++count;
   }
   cout << "Frequency of " << check <<  " = " << count;
   return 0;
}
```

**Output**

```cpp
Number of m = 2
```

## Swap Numbers in Cyclic Order Using Call by Reference

Three variables entered by the user are stored in variables a, b and c respectively.

Then, these variables are passed to the function `cyclicSwap()`. Instead of passing the actual variables, addresses of these variables are passed.

When these variables are swapped in cyclic order in the `cyclicSwap()` function, variables a, band c in the `main` function are also automatically swapped.

### Program to Swap Elements Using Call by Reference

```cpp
#include<iostream>
using namespace std;

void cyclicSwap(int *a, int *b, int *c);

int main()
{
    int a, b, c;

    cout << "Enter value of a, b and c respectively: ";
    cin >> a >> b >> c;

    cout << "Value before swapping: " << endl;
    cout << "a, b and c respectively are: " << a << ", " << b << ", " << c << endl;

    cyclicSwap(&a, &b, &c);

    cout << "Value after swapping numbers in cycle: " << endl;
    cout << "a, b and c respectively are: " << a << ", " << b << ", " << c << endl;

    return 0;
}

void cyclicSwap(int *a, int *b, int *c)
{
    int temp;
    temp = *b;
    *b = *a;
    *a = *c;
    *c = temp;
}
```

**Output**

```cpp
Enter value of a, b and c respectively: 1
2
3
Value before swapping: 
a=1
b=2
c=3
Value after swapping numbers in cycle:
a=3
b=1
c=2
```

Notice that we haven't returned any values from the `cyclicSwap()` function.

## Access Elements of an Array Using Pointer

```cpp
#include <iostream>
using namespace std;

int main()
{
   int data[5];
   cout << "Enter elements: ";

   for(int i = 0; i < 5; ++i)
      cin >> data[i];

   cout << "You entered: ";
   for(int i = 0; i < 5; ++i)
      cout << endl << *(data + i);

   return 0;
}
```

**Output**

```cpp
Enter elements: 1
2
3
5
4
You entered: 1
2
3
5
4
```

In this program, the five elements are entered by the user and stored in the integer array data. Then, the data array is accessed using a for loop and each element in the array is printed onto the screen. Visit this page to learn about [relationship between pointer and arrays](https://www.programiz.com/cpp-programming/pointers-arrays).

