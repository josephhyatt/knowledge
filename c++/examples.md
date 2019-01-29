# Examples

## C++ creating static class

```cpp
#include <iostream> 
using namespace std; 

class Example { 
   public :  
   static int a; 
   static int func(int b) {
      cout << "Static member function called";
      cout << "\nThe value of b is: " << b;
   }
}; 
int Example::a=28;
int main() { 
   Example obj; 
   Example::func(8);     
   cout << "\nThe value of the static data member a is: " << obj.a;
   return 0; 
}  
```

## C++ array index starts from zero

```cpp
#include<iostream> 
using namespace std; 
  
int main() { 
   int arr[] = {5,8,9,3,5}; 
   int i; 
   for(i = 0; i<5; i++)
      cout<< arr[i] <<" ";
      cout<<"\n";
   for(i = 0; i<5; i++)
      cout<< *(arr + i) <<" ";
   return 0;  
}
```

## C++ print size of array parameter

```cpp
#include <iostream> 
using namespace std; 

int func(int a[]) {
   cout << "Size: " << sizeof(a);
   return 0;
}
int main() {
   int array[5]; 
   func(array); 
   cout << "\nSize: " << sizeof(array); 
   return 0;
}
```

## C++ static objects

```cpp
#include <iostream> 
using namespace std; 
class Base {
   public : 
   int func() {
      int a = 20;  
      cout << "The value of a : " << a;
    }
}; 
int main() {
   static Base b;
   b.func(); 
   return 0;
}
```

## C++ static variables in member functions

```cpp
#include <iostream>
using namespace std; 

class Base { 
   public :  
   int func() {
      static int a;
      static int b = 12;  
      cout << "The default value of static variable a is: " << a;
      cout << "\nThe value of static variable b is: " << b;
   }
}; 
int main() {
   Base b;
   b.func(); 
   return 0;
}
```

## C++ strncpy\(\)

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main () {
   char source[20] = "This is a string";
   char dest[20];
   strncpy(dest, source, 4);
   cout << "The destination string is: " << dest;
   return 0;
}
```

## C++ converting double into a string

```cpp
#include<iostream>
#include<string.h>
using namespace std;

int main() {
   double d = 238649.21316934;
   string s = to_string(d);
   cout << "Conversion of double to string: " << s; 
   return 0;
}
```

## C++ static member variables initialization

```cpp
#include <iostream> 
using namespace std; 

class Demo {   
   public : 
   static int num; 
   int display() {
      cout << "The value of the static member variable num is: " << num;
   }
}; 
int Demo::num = 100;
int main() {
   Demo obj;
   obj.display();
   return 0;
}
```

## C++ Initializing array with variable vs a real number

```cpp
#include <iostream>
using namespace std;

int main() {
   int a = 5;
   int b = 3;
   int arr[4]; 
   arr[0] = a;
   arr[1] = 8;
   arr[2] = b;
   arr[3] = 2;
 
   cout << "The elements of array are: ";
   for(int i = 0; i<4; i++)
      cout << arr[i] << " "; 
   return 0;
}
```

## C++ return local array from function

```cpp
#include<iostream> 
using namespace std; 
int *retArray() { 
   static int arr[10]; 
  
   for(int i = 0; i<10; i++) {
      arr[i] = i+1;
   }  
   return arr; 
}  
int main() { 
   int *ptr = retArray(); 
   cout <<"The array elements are: "; 
   for(int i = 0; i<10; i++) {
      cout<< ptr[i] <<" ";
   }
```

