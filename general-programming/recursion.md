# Recursion

Use recursion to solve the following problems. These problems can also be solved non-recursively; you'll be tempted to use tools that you already understand more deeply, but you must solve each one using recursion. For the first part of these exercises, without using any code, you are expected to identify the followings:

1. What is the input to the program
2. What is the output of the program
3. What is the input to each recursive calls
4. What is the output of each recursive calls

RECURSION EXERCISES

Exercise 1 - Counting Sheep

Write a recursive program that counts how many sheep jumps over the fence. Your program should take a number as an input. That number should be the number of sheep you have. The program should display the number along with the MSG "Another sheep jumps over the fence" until no more sheep left.

1. Input of the program is the Integer of the number of sheep. \(Number\)
2. Output of the program Console log of a message stating "Another sheep jumps over the fence" and the current sheep number
3. The number of sheep decremented 1.
4. Will print out the number of sheep as one less than before, until no sheep are left.

```javascript
function sheepCountDown(num) {
    if(num < 0 ) {
        return;
    }
    console.log('Another sheep jumps over the fence: ' + num + ' sheep left.' );
    sheepCountDown(num -1);
}
sheepCountDown(10);
```

Exercise 2 - Array Double

Write a program that takes an array as input which contains an unknown set of numbers, and output an array which doubles the values of each item in that array. Test your solution by trying a handful of different arrays.

1. Input is an array which contains an unknown set of numbers. \(\[ 4, 6, 9 \]\)
2. Output is an array which conatains double the values of each item in that array. \(\[ 8, 12, 18 \]\)
3. Take an index number of the array, double the value of that index number, increment the index number, when all items within the array have been doubled,returns. \(\[ 4, 6, 9 \], 0\)
4. The output of each recursive call is an array of doubled values. \(\[ 8, 6, 9 \], 1\)

Exercise 3 - Reverse String

Write a program that reverses a string. Take a string as input, reverse the string, and return the new string.

1. The input to the program is a string.
2. The output of the program is that string reversed.
3. The input to the recursive call will grab the individual last character at he end of the string and put it first.
4. The output of the recursive call is the returned new string with the character put the end \(just add char to the string\).

Exercise 4 - nth Triangular Number

Calculates the nth triangular number. A triangular number counts the objects that can form an equilateral triangle. The nth triangular number is the number of dots composing a triangle with n dots on a side, and is equal to the sum of the n natural numbers from 1 to n. This is the Triangular Number Sequence: 1, 3, 6, 10, 15, 21, 28, 36, 45

```text
                      *
        *           *    *
```

* ```text
  |   *   *  |   *    *    *  |
  ```

1st 2nd 3rd nth?

1. The input to the program \(4\)
2. The output of the program \(10\)
3. The input to each recursive call \(1\) - \(2\) - \(3\) - \(4\) - \(5\)
4. The output of each recursive call \(1\) - \(3\) - \(6\) - \(10\) - \(15\) So the sequence is whatever input number + the numbers before

Exercise 5 - String Splitter

Split a string based upon a separator \(similar to String.prototype.split\).

1. What is the input to the program
2. What is the output of the program
3. What is the input to each recursive calls
4. What is the output of each recursive calls

Notes for later: have to use substring and splitter

Exercise 6 - Binary Representation

Write a recursive function that prints out the binary representation of a given number. For example, the program should take 3 as an input and print 11 as output, or 25 as an input and print 11001 as an output. Note that the binary representation of 0 should be 0.

1. What is the input to the program
2. What is the output of the program
3. What is the input to each recursive calls
4. What is the output of each recursive calls

Exercise 7 - Anagrams

An anagram is any word or phrase that exactly reproduces the letters in another order. Write a program that creates an anagram \(listing all the rearrangements of a word\) of a given word. For example, if the user types east, the program should list all 24 permutations, including eats, etas, teas, and non-words like tsae.

Hint: For your algorithm, you might want to think about a prefix and use that to create the new words. For example, given east, use e as a prefix and you would place e in front of all six permutations of ast — ast, ats, sat, sta, tas, and tsa. This will give you the words east, eats, esat, esta, etas, and etsa. Continue this way until you find all the anagrams for east. There should be 24 of them.

1. What is the input to the program
2. What is the output of the program
3. What is the input to each recursive calls
4. What is the output of each recursive calls

Exercise 8 - Animal Hierarchy

Step through the code and find the input to the program, input to each recursive calls, output of each recursive calls and the output of the program. The purpose of this exercise is not for you to copy paste the code and find out the output but rather step through each line, analyze each step to understand how recursion works.

const AnimalHierarchy = \[ {id: 'Animals','Parent': null}, {id: 'Mammals','Parent': 'Animals'}, {id: 'Dogs','Parent':'Mammals' }, {id: 'Cats','Parent':'Mammals' }, {id: 'Golden Retriever','Parent': 'Dogs'}, {id: 'Husky','Parent':'Dogs' }, {id: 'Bengal','Parent':'Cats' } \]

// ============================== function traverse\(AnimalHierarchy, parent\) { let node = {}; AnimalHierarchy.filter\(item =&gt; item.Parent === parent\) .forEach\(item =&gt; node\[item.id\] = traverse\(AnimalHierarchy, item.id\)\); return node;  
} console.log\(traverse\(AnimalHierarchy, null\)\);

1. What is the input to the program
2. What is the output of the program
3. What is the input to each recursive calls
4. What is the output of each recursive calls

Exercise 9 - Factorial

Write a recursive program that finds the factorial of a given number. The factorial of a number can be found by multiplying that number by each number between itself and one. The factorial of 5 is equal to 5 \* 4 \* 3 \* 2 \* 1 = 120

1. What is the input to the program
2. What is the output of the program
3. What is the input to each recursive calls
4. What is the output of each recursive calls

Exercise 10 - Fibonacci

Write a recursive program that prints the fibonacci sequence of a given number. The fibonnaci sequence a series of numbers in which each number is the sum of the two preceding numbers. For example the 7th fibonacci number in a fibonaci sequence is 13. The sequence looks as follows: 1 1 2 3 5 8 13.

1. What is the input to the program
2. What is the output of the program
3. What is the input to each recursive calls
4. What is the output of each recursive calls

Exercise 11 - Organization Chart

Write a recursive program that prints the following organization chart. Your output should show the output to be as shown below with proper indentation to show the hierarchy.

Zuckerberg Schroepfer Bosworth Steve Kyle Andra Zhao Richie Sofia Jen Schrage VanDyck Sabrina Michelle Josh Swain Blanch Tom Joe Sandberg Goler Eddie Julie Annie Hernandez Rowi Inga Morgan Moissinac Amy Chuck Vinni Kelley Eric Ana Wes

