# Big O Notation

Say you order Harry Potter: Complete 8-Film Collection \[Blu-ray\] from Amazon and download the same film collection online at the same time. You want to test which method is faster. The delivery takes almost a day to arrive and the download completed about 30 minutes earlier. Great! So it’s a tight race.AdvertisementWhat if I order several Blu-ray movies like The Lord of the Rings, Twilight, The Dark Knight Trilogy, etc. and download all the movies online at the same time? This time, the delivery still take a day to complete, but the online download takes 3 days to finish.

For online shopping, the number of purchased item \(input\) doesn’t affect the delivery time. The output is constant. We call this **O\(1\)**.

For online downloading, the download time is directly proportional to the movie file sizes \(input\). We call this **O\(n\)**.

From the experiments, we know that online shopping scales better than online downloading. It is very important to understand big O notation because it helps you to analyze the **scalability** and **efficiency** of algorithms.

**Note:** Big O notation represents the **worst-case scenario** of an algorithm. Let’s assume that O\(1\) and O\(n\) are the worst-case scenarios of the example above.

## What you need to know

### **Here is what I have absorbed in order to prepare myself**

To set the scene for “Big O,” we first need to acknowledge that **software is, of course, heavily based on data**. Huge mountains of data. And making use of that data is what coding is for. In order for a program to make use of data, it often needs to start by sorting that data into a logical order. Whether that is alphabetically, chronologically, by size, by date, and so on.

**Sorting** happens CONSTANTLY, and actually **represents a huge portion of all computer and internet activity.** I’ve heard programmers state that “Quick Sort is pretty much what runs all of the internet”.

What do they mean by that? Well sorting data is its own entire subsection within the study of computer science, and there are many well-defined algorithms for sorting. There is **Quick Sort, Bubble Sort, Selection Sort, Merge Sort, Heap Sort** and many more. Each with different approaches to get to the same or similar results.

![](https://cdn-images-1.medium.com/max/800/1*PckWInXH2fPH6XaPIceeVA.jpeg)

## **But which one is best if they \(almost\) all return the same result?**

Best usually means which is fastest. This is where “Big O” came into play.

Big O notation, sometimes also called “asymptotic analysis”, primarily **looks at how many operations a sorting algorithm takes to completely sort a very large collection of data.** This is a measure of efficiency and is how you can directly compare one algorithm to another.

When building a simple app with only a few pieces of data to work through, this sort of analysis is unnecessary. But when working with very large amounts of data, like a social media site or a large e-commerce site with many customers and products, **small differences between algorithms can be significant.**

## **Big O notation ranks an algorithms’ efficiency**

It does this with regard to “**O**” and “**n**”, \( example: “_O\(log n\)” \)_, where

* **O** refers to the order of the function, or its growth rate, and
* **n** is the length of the array to be sorted.

Let’s work through an example. If an algorithm has the number of operations required formula of:

_**f**_**\(n\) = 6n^4 - 2n^3 + 5**

As “**n**” approaches infinity \(for very large sets of data\), of the three terms present, **6n^4** is the only one that matters. So the lesser terms, **2n^3** and **5**, are actually just omitted because they are insignificant. Same goes for the “**6**” in **6n^4**, actually.

## **Therefore, this function would have an order growth rate, or a “big O” rating, of O\(n^4\) .**

When looking at many of the most commonly used sorting algorithms, ****the rating of **O\(n log n\)** in general is the best that can be achieved. Algorithms that run at this rating include Quick Sort, Heap Sort, and Merge Sort. **Quick Sort** is the standard and is used as the default in almost all software languages.

![](https://cdn-images-1.medium.com/max/800/1*KfZYFUT2OKfjekJlCeYvuQ.jpeg)

It is important to note that **there is no single algorithm that is fastest in all cases**, as data can be input into a program in all manners of states. And the approaches of each algorithm will have a best case and worst case scenario where they perform at their best or worst.

While Quick Sort is the standard, it also competes with Merge Sort and Heap Sort, which are other O\(n log n\) rated sorting algorithms. There are scenarios where those are used instead.

The most direct competitor of Quick Sort is **Heap Sort.** Heap Sort’s running time is also O\(n log n\), but Heap Sort’s average running time is usually considered slower than in-place Quick Sort.

Merge Sort is a **stable sort**, which means it preserves the input order of equal elements in the output, unlike standard in-place Quick Sort and Heap Sort.

**Bubble / Insertion / Selection Sort run at O\(n²\)**, which in terms of number of operations **can take significantly longer** than those listed above rated at O\(n log n\) when dealing with really big data. But there can be scenarios where the others are faster depending on the data.

There are also times where something that is very simple, such as Counting Sort, is great, because it is much faster to write up and much easier to visualize and comprehend.

Sometime you not only need to consider the time demands of an algorithm, but also the data-space demands as well \(or perhaps even more so\). Some algorithms also operate with a smaller storage footprint.

![](https://cdn-images-1.medium.com/max/800/1*v8QUkNaqnh0ItUWgtwpP5g.jpeg)

## Why do you need to know all this?

So after all that, if you always just resort to using a language’s built-in sorting algorithm, \(which is based on Quick Sort\), then why care about sorting algorithms and “Big O”? Why would companies ask you about it in an interview?

The answer is that studying Big O notation makes you grasp the very important concept of efficiency in your code. So when you do work with huge data sets, you will have a good sense of where major slowdowns are likely to cause bottlenecks, and where more attention should be paid to get the largest improvements. This is also called sensitivity analysis, and is an important part of solving problems and writing great software.

So if you are trying to prepare for your first interview, or perhaps you struggled in your last one, increasing your knowledge on concepts like Big O Notation and other computer science topics will help give you a leg up. You’ll be better equipped to demonstrate your potential and impress to land that position.

## Real-Life Big-O

Many “operations” in real life can help us with finding what the order is. When analyzing algorithms/operations, we often consider the worst-case scenario. What’s the worst that can happen to our algorithm and when does our algorithm need the most instructions to complete the execution? Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations.

Let’s assume I am standing in the front of a class of students and one of them has my bag. Here are few scenarios and ways in which I can find my bag and their corresponding order of notation.

#### O\(n\) — Linear Time:

**Scenario:** Only one student in my class who hid my bag knows about it.

**Approach:** I will have to ask each student individually in the class if they have my bag. If they don’t, I move on to ask the next student.

**Worst-Case Scenario:** In the worst case scenario, I will have to ask questions.

```javascript
def search_for_bag(data):
    found = False
    for i,name in enumerate(data):
        # Have to go through each student to find who has my bag
            if data[name] is True:
                found = True
                return name

data = {
    'Jane' : False,
    'James' : False,
    'Jon' : False,
    'Joe': True
    } 
print(search_for_bag(data)) #Joe has my bag.
#o/p: The bag is with Joe

```

**Explanation:**

1. Here, given an input of size n, the number of steps required is directly related to the amount of data it is processing.
2. Single for loops, linear search are examples of linear time
3. In above example, an array size/input size increases, time to find desired value also increases.

#### O\(1\) — Constant Time

**Scenario:** Student who hid my bag name is known to me.

**Approach** : Since I know _Joe_ has my bag, I’ll directly ask him to give it to me.

**Show me the code!**

```javascript
#If I know the persons name, I have to take only one step to check
def get_bag(name):
    return data[name]
data = {
    'Jane' : False,
    'James' : False,
    'Jon' : False,
    'Joe': True
    }
print("Is bag with Joe ? " +str(get_bag('Joe')))
#o/p: Is bag with Joe ? True
```

**Explanation:**

1. Here, given an input of size n, it only takes a one step for the algorithm to accomplish the task.
2. An algorithm takes same time\(constant time\) to execute irrespective of the amount of data.
3. This algorithm is not affected by the array size either.

#### O\(n²\) — Quadratic Time:

**Scenario:** In the entire class, only one student knows on which student desk my bag is hidden.

**Approach:** I will start questioning each student individually and ask him about all the others students too. If I don’t get the answer from the first student, I will move on to the next one.

**Worst-Case Scenario:** In the worst case scenario, I will have to ask _n2_questions, questioning each student about other students as well.

**Show me the code!**

```javascript
def search_bag(data):
    n = len(data)
    for x in range(n):
       answer = input("Do you have my bag, "+data[x] + "?")
       # each student individually if they have my bag
       if answer == 'yes':
         return "Ha! Found it "+ data[x] + "had my bag"
       else:
        # If they don't have it, ask about all other students.
         for y in range(x+1, n):
            new_answer = input("You think my bag is with " +data[y])
            if new_answer == 'yes':
                return 'Your bag is with '+data[y]
data=  ['Jane','James','Jon', 'Joe']  # Here Joe has the bag
print(search_bag(data))
```

**Explanation:**

1. Here, given an input of size n, the number of steps it takes to accomplish a task is square of n.
2. Each pass to outer loop O\(n\) requires going through entire list through the inner-loop.
3. Nested for-loops are example of quadratic time as we run a linear operation within other linear operation

#### O\(log n\) — Logarithmic time:

**Scenario:** Here, all the students know who has my bag but will only tell me if I guessed the right name.

**Approach:** I will divide the class in half, then ask: “Is my bag on the left side, or the right side of the class?” Then I take that group and divide it into two and ask again, and so on.

**Worst Case Scenario:** In the worst case, I will have to ask _log n_ questions.

**Show me the code!**

```javascript
def binary_bag_search(data, target, low = 0, high = None):
    if high is None:
        high = len(data)-1
    if low > high :
        return False
    else:
        mid = (low + high)// 2
        if data[mid] == target:
            return True
        elif data[mid] > target:
           return binary_search(data, target, low, mid-1)
        else:
            return binary_search(data,target, mid+1, high)
data=  ['Jane','James','Jon', 'Joe']  # Here Joe has the bag
found = binary_bag_search(data, 'Joe')
print("Bag Found ?" + found)
```

**Explanation:**

1. Here, given an input of size n, the number of steps it takes to accomplish the task are decreased by roughly 50% each time through the algorithm.
2. O \(log N\) algorithms are very efficient because increasing amount of data has little effect at some point early on because the amount of data is halved on each run through.
3. Binary search is a perfect example of this.

#### 

