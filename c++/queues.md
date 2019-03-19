# Queues

Queues are a type of container adaptors which operate in a first in first out \(FIFO\) type of arrangement. Elements are inserted at the back \(end\) and are deleted from the front.

**The functions supported by queue are :**

1. [empty\(\)](https://www.geeksforgeeks.org/queueempty-queuesize-c-stl/) – Returns whether the queue is empty.
2. [size\(\)](https://www.geeksforgeeks.org/queueempty-queuesize-c-stl/) – Returns the size of the queue.
3. [queue::swap\(\) in C++ STL](https://www.geeksforgeeks.org/queue-swap-cpp-stl/): Exchange the contents of two queues but the queues must be of same type, although sizes may differ.
4. [queue::emplace\(\) in C++ STL](https://www.geeksforgeeks.org/queueemplace-c-stl/): Insert a new element into the queue container, the new element is added to the end of the queue.
5. [queue::front\(\) and queue::back\(\) in C++ STL](https://www.geeksforgeeks.org/queuefront-queueback-c-stl/)– **front\(\)** function returns a reference to the first element of the queue. **back\(\)** function returns a reference to the last element of the queue.
6. [push\(g\) and pop\(\)](queue::push%28%29%20and%20queue::pop%28%29%20in%20C++%20STL) – **push\(\)** function adds the element ‘g’ at the end of the queue. **pop\(\)** function deletes the first element of the queue.

## Queues Example

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() 
    {
    cout << "\nC++ Queue Code" << endl;
    
    /* Queues are First-In/First-Out. This is like a line to pay when shopping. The first person to enter the line is the first person to get to a register to pay for their items. */
    
    // Create a queue that holds integers.
    queue<int> q;
    
    // Add some numbers to the stack.
    q.push(4);
        q.push(2);
    q.push(1);
    q.push(3);
    
    // The stack should be 4 > 2 > 1 > 3, with 4 in front, since that's the order we pushed them in.
    
    // Print each number and remove it from the queue.
    cout << "Printed queue: " << endl;
    while(q.empty() == false)
        {
        int frontnum = q.front(); // Look at what the front of the queue is.
        cout << frontnum << " ";
        q.pop(); // Remove the top item from the stack.
        }
        cout << endl;
        
        // Let's look at a queue of nodes. 
        /* NOTICE: This is the same as stacks, except the default queue creation (queue<Food*> foodstack;) is the only difference. */
        
        struct Food
                {
                // The three variables we care about.
                bool tastesGood;
                int quantity;
                string name;
                
                // Constructor for this node.
                Food(bool taste, int quant, string n)
                        {
                        tastesGood = taste;
                        quantity = quant;
                        name = n;
                        }
                        
                // Default constructor if no info is given.
                Food(): tastesGood(false), quantity(0), name("Air") {}
                };
        
        /* Node initialization is as such
   Food* myFood = new Food(true, 100, "chicken");
   cout << myFood->name << endl;
   */
        
        
        // Create our queue of foods.
        queue<Food*> foodq;
        
        // Add some nodes to this queue.
        foodq.push(new Food(false, 1, "Apple"));
        foodq.push(new Food(true, 2, "Banana"));
        foodq.push(new Food(true, 5, "Eclair"));
        foodq.push(new Food(true, 3, "Chocolate"));
        foodq.push(new Food(true, 4, "French Fries"));

        
        // Print each food in our queue. (It'll go in the order we placed them in the queue, regardless of content.)
        cout << endl << "Printed Food queue: " << endl;
        int counter = 0;
        while(foodq.empty() == false)
                {
                counter += 1;
                Food* food = foodq.front();
                foodq.pop();
                cout << "Food number " << counter << " has " << food->quantity << " of " << food->name << " and it ";
                if(food->tastesGood == true)
                        {
                        cout << "tastes good!" << endl;
                        }
                else
                        {
                        cout << "tastes bad!" << endl;
                        }
                }
        
        return 0;
    }
    
// Output: 
4 2 1 3 

Printed Food queue: 
Food number 1 has 1 of Apple and it tastes bad!
Food number 2 has 2 of Banana and it tastes good!
Food number 3 has 5 of Eclair and it tastes good!
Food number 4 has 3 of Chocolate and it tastes good!
Food number 5 has 4 of French Fries and it tastes good!
```

>

