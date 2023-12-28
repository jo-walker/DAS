## Intro 2 DS & Algorithms
Designs efficient software. DA==how data is stored on a computer && A's==problem solving procedure performing.

## How is DS applied in computing
Stores data to enable efficient access and modification. The choice of the DS varies depending on the cases:
* **Arrays:** Contigious block of memory that stores a fixed size (immutable) sequence of elems of the same type. Good for storing and retrieving data. Not good for addition or removal of elems.
* **Stacks:** linear, follows LIFO principle. elems are added on top of the stack (pushed) and removed from the top (popped). Used in function call stack in PL's and 'undo' operations in software apps.
* **Queues:** linear, adheres to FIFO. Elems are added at the end of the queue (enqueued) and removed from the front end (dequeued). Used to process data input order such as task scheduling or event handling in computer systems.
* **Linked List:** dynamic sequence of data elems; termed nodes, where each node has a value & a pointer to the next node->allows efficient insertion and removal of elems at any position in the list.
* **Trees:** hierarchical; nodes in multiple lvl's. each node may have one || many child nodes and the top upmost is called root. Used for representing hierarchical relationships like the structure of a filesystem or organizational charts. 
* **Graphs:** set of nodes (vertices) connected by edges, which can be one-way (directed) || two-way (undirected). used to model complex relationships and connections between elems such as social networks, web pages (links), and routes between locations. 

![ds](https://user-images.githubusercontent.com/37275728/185381435-9335db5b-8c9a-4e74-87dc-deac3c0356f1.png)

## How is A's applied in computing
Solves specific problems or performs tasks by procedural instructions. The efficiency is evaluated by time complexity and space complexity.
~=akin to recipe with series of steps to achieve a certain outcome. Characteristics of a good A:
* **Input:** The data that the algorithm uses for its operation.
* **Output:** The result produced by the algorithm.
* **Definiteness:** Every step in the algorithm should be unambiguous and precisely defined.
* **Finiteness:** The algorithm must terminate after a finite number of steps.
* **Effectiveness:** Each step of the algorithm should be simple and executable, contributing towards the final output.

(!)It's important to note that unlike algorithms, which must always terminate, some programs are designed to run indefinitely until interrupted by an external action. For instance, an operating system is a program that runs in a continuous loop until the computer is turned off.

### Types of A's
can be classified into | types based on their problem domain and the strategy they adopt for problem-solving. Some common categories:

* **Sorting Algorithms:** organizes data in a certain order -> asc or desc such as bubble sort, insertion sort, selection sort, quick sort, and merge sort.
  
```
1: Bubble Sort: adjacent elements are compared and swapped <- they are in wrong order.
The pass is repeated til the entire list is sorted.
Time complexity == O(n^2) in the worst case.
---------------------
Initial Array: [5, 3, 8, 4, 2]


After 1st Pass: [3, 5, 4, 2, 8]
After 2nd Pass: [3, 4, 2, 5, 8]
After 3rd Pass: [3, 2, 4, 5, 8]
After 4th Pass: [2, 3, 4, 5, 8] (Sorted)
```
```
2: Insertion Sort:
   Builds the final sorted array one elem at a time.
   Takes each elem and inserts it intoto its correct pos in the sorted part of the array.
   Time complexity == O(n^2) in the worst case.
   ---------------------
   Initial Array: [5, 3, 8, 4, 2]

   After 1st Pass: [3, 5, 8, 4, 2]
   After 2nd Pass: [3, 4, 5, 8, 2]
   After 3rd Pass: [2, 3, 4, 5, 8] (Sorted)
```
```
3: Selection Sort:
   Divides the list into a sorted and an unsorted region.
   Repeatedly selects the smallest (or largest) element from the unsorted region and swaps it with the first element of the unsorted region.
   Time complexity == O(n^2) in the worst case.
   ---------------------
   Initial Array: [5, 3, 8, 4, 2]

   After 1st Pass: [2, 3, 8, 4, 5]
   After 2nd Pass: [2, 3, 4, 8, 5]
   After 3rd Pass: [2, 3, 4, 5, 8] (Sorted)
```
```
4: Quick Sort:
   Chooses a pivot elem & partitions the array into two sub-arrays.
   Recursively sorts the sub-arrays.
   Time complexity == O(n log n) on avg.
   ---------------------
   Initial Array: [5, 3, 8, 4, 2]

   Pivot: 3
   Lesser: [2]
   Greater: [5, 8, 4]

   Pivot: 5
   Lesser: [4]
   Greater: [8]

   Sorted Array: [2, 3, 4, 5, 8]
```
```
5: Merge Sort:
   Divides the array into two => recursively sorts them => merges the sorted halves.
   Time complexity == O(n log n) in the worst case.
    ---------------------
    Initial Array: [5, 3, 8, 4, 2]

   Split: [5, 3] [8, 4, 2]
   Split: [5] [3] [8] [4, 2]
   Merge: [3, 5] [4, 8] [2]
   Merge: [3, 4, 5, 8] [2]

   Sorted Array: [2, 3, 4, 5, 8]
```
```
6: Heap Sort:
   Builds a max (min) heap from the array & repeatedly extracts the root (max or min) elem.
   Time complexity == O(n log n) in the worst case.
   ---------------------
    Initial Array: [5, 3, 8, 4, 2]

    1. max heap,
    2. swap the max w the last elem of the heap => sorted,
    3. exclude the sorted ones,
    4. heapify the root,
    5. repeat 2-4 til size of the heap is 1.

   Heapify: [8, 5, 4, 3,2]
   Extract: [2, 3, 4, 5, 8]

   Sorted Array: [2, 3, 4, 5, 8]
```
```
7: Radix Sort: [TO-DO: scrabble on notepad to visualize]
   Sorts elems by processing individual digits.
   Time complexity == O(nk) [k is the # of digits.]
    ---------------------
   Initial Array: [543, 123, 987, 456, 321]

   Pass 1: [321, 123, 543, 987, 456]
   Pass 2: [123, 321, 543, 456, 987]
   Pass 3: [123, 321, 456, 543, 987]

   Sorted Array: [123, 321, 456, 543, 987]
```

* **Search Algorithms:** find a specific item || value from a collection of data such as linear search, binary search, and depth-first search.

```
Example: Binary Search
----------------------
Searching 33 in Sorted Array: [1, 3, 5, 7, 9, 11, 33, 45, 77, 89]

Mid element at start: 9
33 > 9, so discard left half
New mid element: 45
33 < 45, so discard right half
New mid element: 11
33 > 11, so discard left half
The remaining element is 33, which is the target
```

* **Graph Algorithms:** solve graph-related problems such as finding the shortest path between nodes || verifying if a graph is connected. Examples include Dijkstra's algorithm and the Floyd-Warshall algorithm.

* **String Algorithms:** handle string-related problems like finding the longest common subsequence between two strings || pattern matching in a string. Examples include the Knuth-Morris-Pratt (KMP) algorithm and the Boyer-Moore algorithm.

```
Example: Pattern Matching (Boyer-Moore)
---------------------------------------
Text:    "ABABDABACDABABCABAB"
Pattern: "ABABCABAB"

Pattern matched starting at index 10 in the text.
```
[TO-DO: analyze the followings]
## Understanding Algorithmic Complexity

Algorithmic complexity refers to the computational resources (time or space) an algorithm requires as the input size increases. Various types of complexity are considered when analyzing an algorithm:

* **Best Case Complexity**: This is the minimum time or space required by an algorithm for an input of a particular size. For instance, an algorithm with a best case time complexity of O(1) implies that the algorithm executes in constant time irrespective of the input size.
* **Average Case Complexity**: This signifies the average time or space an algorithm requires for all possible inputs of a given size. Calculating the average case complexity can be more challenging than other types of complexity as it requires understanding the distribution of possible inputs and their respective effect on the algorithm's performance.
* **Worst Case Complexity**: This indicates the maximum time or space an algorithm may take for any input of a certain size. This type of complexity is often the most critical since it provides an upper bound on the algorithm's execution time, thus offering predictability.
* **Space Complexity**: It represents the total amount of memory space that an algorithm needs relative to the input size. Space complexity becomes a key consideration in scenarios where memory resources are limited, and the algorithm's efficiency is crucial.
* **Time Complexity**: It measures the computational time an algorithm takes as the input size grows. Time complexity is the most frequently analyzed type of complexity because the speed of an algorithm often determines its usability.

By understanding these different types of complexities, you can make informed decisions about the right algorithms to use for your specific software development tasks and effectively optimize the efficiency of your programs.

### Analyzing Algorithm Growth Rates

Understanding how the running time or space complexity of an algorithm scales with increasing input size is pivotal in algorithm analysis. To describe this rate of growth, we employ several mathematical notations that offer insights into the algorithm's efficiency under different conditions.

#### Big O Notation (O-notation)

The Big O notation represents an asymptotic upper bound, indicating the worst-case scenario for an algorithm's time or space complexity. Essentially, it signifies an upper limit on the growth of a function.

If we designate $f(n)$ as the actual complexity and $g(n)$ as the function in Big O notation, stating $f(n) = O(g(n))$ implies that $f(n)$, the time or space complexity of the algorithm, grows no faster than $g(n)$.

For instance, if an algorithm has a time complexity of $O(n)$, it signifies that the algorithm's running time does not grow more rapidly than a linear function of the input size, in the worst-case scenario.

#### Big Omega Notation (Ω-notation)

The Big Omega notation provides an asymptotic lower bound that expresses the best-case scenario for the time or space complexity of an algorithm.

If $f(n) = Ω(g(n))$, this means that $f(n)$ grows at a rate that is at least as fast as $g(n)$. In other words, $f(n)$ does not grow slower than $g(n)$.

For example, if an algorithm has a time complexity of $Ω(n)$, it implies that the running time is at the bare minimum proportional to the input size in the best-case scenario.

#### Theta Notation (Θ-notation)

Theta notation offers a representation of the average-case scenario for an algorithm's time or space complexity. It sets an asymptotically tight bound, implying that the function grows neither more rapidly nor slower than the bound.

Stating $f(n) = Θ(g(n))$ signifies that $f(n)$ grows at the same rate as $g(n)$ under average circumstances. This indicates the time or space complexity is both at most and at least a linear function of the input size.

Remember, these notations primarily address the growth rate as the input size becomes significantly large. While they offer a high-level comprehension of an algorithm's performance, the actual running time in practice can differ based on various factors, such as the specific input data, the hardware or environment where the algorithm is operating, and the precise way the algorithm is implemented in the code.

### Diving into Big O Notation Examples

Big O notation is a practical tool for comparing the worst-case scenario of algorithm complexities. Here are examples of various complexities:

* **$O(1)$**: Constant time complexity. Regardless of the input size, the algorithm performs its task in a fixed amount of time. For example, retrieving an item by its index from an array or accessing a key-value pair in a hash map.

* **$O(log n)$**: Logarithmic time complexity. The time taken by the algorithm increases logarithmically with input size, meaning the time taken doubles for each doubling of the input size. Binary search and balanced binary tree operations are typical examples.

* **$O(n)$**: Linear time complexity. The running time of the algorithm scales linearly with the input size. This is characteristic of simple, single-pass processes such as iterating over an array or a linked list.

* **$O(n log n)$**: Log-linear time complexity. The running time grows linearly with the input size, but also logarithmically due to the operations performed. Algorithms such as QuickSort, MergeSort, and HeapSort fall in this category.

* **$O(n^2)$**: Quadratic time complexity. The running time grows with the square of the input size. Nested iterations often have this complexity, with Bubble Sort and Insertion Sort as notable examples.

* **$O(n^3)$**: Cubic time complexity. The running time scales with the cube of the input size. This is common with algorithms involving three nested loops, such as certain naive matrix multiplication algorithms.

* **$O(2^n)$**: Exponential time complexity. The running time doubles with each addition to the input data set. This behavior is seen in many brute-force algorithms, like generating all subsets of a set or the naive solution to the Travelling Salesman Problem.

The graph below illustrates the growth of these different time complexities:

![big_o](https://user-images.githubusercontent.com/37275728/185381461-ec062561-1f55-4cf5-a3fa-d4cc0a2c06df.png)

The choice of an algorithm significantly impacts the application's performance, making the understanding of time complexity crucial.

### Interpreting Big O Notation: Key Rules

1. **Neglect Constant Factors**: In Big O notation, we are interested in the rate of growth, not the exact number of operations. Therefore, constant factors are typically ignored. For example, the function $5n$ is represented as $O(n)$, discarding the constant factor of 5.

2. **Omit Smaller Terms**: For functions with multiple terms, only the term with the fastest growth rate is considered significant. If an algorithm's running time is $n^2 + n$, its time complexity would be $O(n^2)$, as $n^2$ grows faster than $n$.

3. **Consider Upper Bounds**: Big O notation defines an upper limit on the growth rate of a function. If an algorithm has a time complexity of $O(n)$, it can also be described as $O(n^2)$, $O(n^3)$, and so on. But, it does not mean that an algorithm with $O(n^2)$ complexity is also $O(n)$, because Big O notation does not provide a lower bound on growth.

4. **$n$ and $log n$ Dominate Constants**: In Big O notation, terms that grow at least as fast as $n$ or $log n$ are dominant over constant terms. For instance, in the complexity $O(n + k)$, the $n$ term is dominant, resulting in a simplified complexity of $O(n)$.

### Can every problem have an O(1) algorithm?

- Not every problem has an algorithm that can solve it, irrespective of the complexity. For instance, the Halting Problem is undecidable—no algorithm can accurately predict whether a given program will halt or run indefinitely on every possible input.
- Sometimes, we can create an illusion of $O(1)$ complexity by precomputing the results for all possible inputs and storing them in a lookup table (like a hash table). Then, we can solve the problem in constant time by directly retrieving the result from the table. This approach, known as memoization or caching, is limited by memory constraints and is only practical when the number of distinct inputs is small and manageable.
- Often, the lower bound complexity for a class of problems is $O(n)$ or $O(nlogn)$. This bound represents problems where you at least have to examine each element once (as in the case of $O(n)$) or perform a more complex operation on every input (as in $O(nlogn)$), like sorting. Under certain conditions or assumptions, a more efficient algorithm might be achievable.
  
### When do algorithms have O(logn) or O(nlogn) complexity?

The exact time complexity of an algorithm usually stems from how the size of the input affects the execution flow of the algorithm—particularly the loop iterations. 

Consider four example algorithms with differing complexities:

1. **First Algorithm** ($O(n)$): Here, the running time is directly proportional to the input size ($n$), as each loop iteration reduces $n$ by 1. Hence, the number of iterations equals the initial value of $n$.

```python
WHILE n > 0:
    n = n - 1
```

2. **Second Algorithm** ($O(log(n))$): In this case, the running time is proportional to the number of times the loop can iterate before $n$ reduces to 0. Each loop iteration halves the value of $n$. This equals the number of times you can halve $n$ before it becomes 0, which also corresponds to $log(n)$.

```python
WHILE n > 0:
   n = n / 2
```

3. **Third Algorithm** ($O(nlog(n))$): Here, the outer loop iterates $n$ times, and the inner loop iterates $log(n)$ times for each outer loop iteration. Hence, the total number of iterations is $n * log(n)$.

```python
m = n
WHILE m > 0:
   k = n
   WHILE k > 0:
      k = k / 2
   m = m - 1
```

4. **Fourth Algorithm** ($O(log^2(n))$): In this scenario, the outer loop iterates $log(n)$ times, and the inner loop also iterates $log(n)$ times for each outer loop iteration. Consequently, the total number of iterations equals $log^2(n)$.

```python
m = n
WHILE m > 0:
   k = n
   WHILE k > 0:
      k = k / 2
   m = m / 2
```

### Misconceptions

* **Need for Formal Proof**: Formal proof of Big O complexity is rarely necessary in everyday programming or software engineering. However, having a fundamental understanding of theoretical complexity is crucial when selecting appropriate algorithms, especially when solving complex problems. It aids in understanding the trade-offs between different solutions and predicting the algorithm's performance.

* **Practical Application of Big O**: It's not essential to assign Big O complexity for every single function or chunk of code you write. However, if you're dealing with large datasets or performance-critical applications, understanding the time and space complexity of your algorithms and data structures can help you make informed decisions about scalability and efficiency.

* **Exact Performance Predictor**: Big O notation is not a predictor of an algorithm's precise running time for a given input size. Instead, it provides an upper bound on the growth rate of the algorithm's running time or space usage as the input size increases. It's a tool to compare the scalability of different algorithms, ignoring implementation details and specific characteristics of the input data.

* **Real-world Performance**: In real-world scenarios, the actual running time of an algorithm can be influenced by various factors, including the specific characteristics of the input data, the efficiency of the implementation, and the hardware and software environment in which it runs. Big O notation doesn't account for these factors.

* **Optimization vs. Readability**: While it's crucial to consider performance, it shouldn't come at the cost of code readability and maintainability. Clear, simple code is often more valuable than highly optimized code, especially if the optimizations complicate the code without offering substantial performance improvements. Instead of optimizing every detail, focus on identifying and addressing the actual bottlenecks in your code, as these are the areas where optimizations can make a significant difference.