# Efficient Sorting Basics

## **Merge Sort**

**Definition:**

* A comparison based sorting algorithm
  * Divides entire dataset into groups of at most two.
  * Compares each number one at a time, moving the smallest number to left of the pair.
  * Once all pairs sorted it then compares left most elements of the two leftmost pairs creating a sorted group of four with the smallest numbers on the left and the largest ones on the right.
  * This process is repeated until there is only one set.

**What you need to know:**

* This is one of the most basic sorting algorithms.
* Know that it divides all the data into as small possible sets then compares them.

**Big O efficiency:**

* Best Case Sort: Merge Sort: O\(n\)
* Average Case Sort: Merge Sort: O\(n log n\)
* Worst Case Sort: Merge Sort: O\(n log n\)

## **Quicksort**

**Definition:**

* A comparison based sorting algorithm
  * Divides entire dataset in half by selecting the average element and putting all smaller elements to the left of the average.
  * It repeats this process on the left side until it is comparing only two elements at which point the left side is sorted.
  * When the left side is finished sorting it performs the same operation on the right side.
* Computer architecture favors the quicksort process.

**What you need to know:**

* While it has the same Big O as \(or worse in some cases\) many other sorting algorithms it is often faster in practice than many other sorting algorithms, such as merge sort.
* Know that it halves the data set by the average continuously until all the information is sorted.

**Big O efficiency:**

* Best Case Sort: Merge Sort: O\(n\)
* Average Case Sort: Merge Sort: O\(n log n\)
* Worst Case Sort: Merge Sort: O\(n^2\)

## **Bubble Sort**

**Definition:**

* A comparison based sorting algorithm
  * It iterates left to right comparing every couplet, moving the smaller element to the left.
  * It repeats this process until it no longer moves and element to the left.

**What you need to know:**

* While it is very simple to implement, it is the least efficient of these three sorting methods.
* Know that it moves one space to the right comparing two elements at a time and moving the smaller on to left.

**Big O efficiency:**

* Best Case Sort: Merge Sort: O\(n\)
* Average Case Sort: Merge Sort: O\(n^2\)
* Worst Case Sort: Merge Sort: O\(n^2\)

**Merge Sort Vs. Quicksort**

* Quicksort is likely faster in practice.
* Merge Sort divides the set into the smallest possible groups immediately then reconstructs the incrementally as it sorts the groupings.
* Quicksort continually divides the set by the average, until the set is recursively sorted.



## Array Sorting Algorithms \(cheat sheet\)

| Algorithm | Time Complexity | Time Complexity | Time Complexity | Space Complexity |  |
| :---: | :---: | :---: | :---: | :---: | :--- |
|  | Best | Average | Worst | Worst |  |
| [Quicksort](http://en.wikipedia.org/wiki/Quicksort) | `Ω(n log(n))` | `Θ(n log(n))` | `O(n^2)` | `O(log(n))` |  |
| [Mergesort](http://en.wikipedia.org/wiki/Merge_sort) | `Ω(n log(n))` | `Θ(n log(n))` | `O(n log(n))` | `O(n)` |  |
| [Timsort](http://en.wikipedia.org/wiki/Timsort) | `Ω(n)` | `Θ(n log(n))` | `O(n log(n))` | `O(n)` |  |
| [Heapsort](http://en.wikipedia.org/wiki/Heapsort) | `Ω(n log(n))` | `Θ(n log(n))` | `O(n log(n))` | `O(1)` |  |
| [Bubble Sort](http://en.wikipedia.org/wiki/Bubble_sort) | `Ω(n)` | `Θ(n^2)` | `O(n^2)` | `O(1)` |  |
| [Insertion Sort](http://en.wikipedia.org/wiki/Insertion_sort) | `Ω(n)` | `Θ(n^2)` | `O(n^2)` | `O(1)` |  |
| [Selection Sort](http://en.wikipedia.org/wiki/Selection_sort) | `Ω(n^2)` | `Θ(n^2)` | `O(n^2)` | `O(1)` |  |
| [Tree Sort](https://en.wikipedia.org/wiki/Tree_sort) | `Ω(n log(n))` | `Θ(n log(n))` | `O(n^2)` | `O(n)` |  |
| [Shell Sort](http://en.wikipedia.org/wiki/Shellsort) | `Ω(n log(n))` | `Θ(n(log(n))^2)` | `O(n(log(n))^2)` | `O(1)` |  |
| [Bucket Sort](http://en.wikipedia.org/wiki/Bucket_sort) | `Ω(n+k)` | `Θ(n+k)` | `O(n^2)` | `O(n)` |  |
| [Radix Sort](http://en.wikipedia.org/wiki/Radix_sort) | `Ω(nk)` | `Θ(nk)` | `O(nk)` | `O(n+k)` |  |
| [Counting Sort](https://en.wikipedia.org/wiki/Counting_sort) | `Ω(n+k)` | `Θ(n+k)` | `O(n+k)` | `O(k)` |  |
| [Cubesort](https://en.wikipedia.org/wiki/Cubesort) | `Ω(n)` | `Θ(n log(n))` | `O(n log(n))` | `O(n)` |  |

