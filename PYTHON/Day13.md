<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day12.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day14.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>


## **Day 13: Understanding Recursion in Python**

### **What is Recursion?**
Recursion is a technique in programming where a function calls itself in order to solve a problem. The idea is to break down a problem into smaller, more manageable parts, with each call solving a smaller instance of the same problem.

### **Basic Concept of Recursion:**
In recursive functions, you will generally have two main components:
1. **Base Case**: This is the condition that stops the recursion. Without it, the function would call itself indefinitely, leading to a stack overflow.
2. **Recursive Case**: This is the part of the function where the recursion happens, calling the function itself with modified arguments.

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=XYwJKFB8DUk&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=30&ab_channel=CodeWithHarry)**
---

### **How Does Recursion Work?**

Let’s break down the process with an example of calculating the factorial of a number.

#### **Factorial Example:**
The factorial of a number \( n \) is defined as:
- \( n! = n \times (n-1) \times (n-2) \times ... \times 1 \)
- The base case: \( 1! = 1 \)

##### **Recursive Formula**:
- Base case: \( factorial(1) = 1 \)
- Recursive case: \( factorial(n) = n \times factorial(n-1) \)

### **Basic Syntax:**
```python
def factorial(n):
    if n == 1:  # Base case
        return 1
    else:  # Recursive case
        return n * factorial(n - 1)
```

#### **How this works:**
Let’s say we want to calculate `factorial(5)`:
1. `factorial(5)` calls `factorial(4)`, and multiplies by 5.
2. `factorial(4)` calls `factorial(3)`, and multiplies by 4.
3. `factorial(3)` calls `factorial(2)`, and multiplies by 3.
4. `factorial(2)` calls `factorial(1)`, and multiplies by 2.
5. `factorial(1)` hits the base case and returns 1.

Now, the recursion unwinds:
- `factorial(2)` returns `2 * 1 = 2`
- `factorial(3)` returns `3 * 2 = 6`
- `factorial(4)` returns `4 * 6 = 24`
- `factorial(5)` returns `5 * 24 = 120`

So, the result of `factorial(5)` is `120`.

---

### **Visualizing the Recursive Call Stack**
When you run the recursive function, Python keeps track of each function call until the base case is reached. The call stack grows as each recursive call is made and unwinds once the base case is hit.

Here’s how the call stack looks:

```
factorial(5)
    -> factorial(4)
        -> factorial(3)
            -> factorial(2)
                -> factorial(1)  # Base case reached
```

Once `factorial(1)` is returned, the recursion unwinds, multiplying the values as described earlier.

---

### **Why Use Recursion?**
Recursion is especially useful for solving problems that have a repetitive structure or can be divided into smaller subproblems of the same type. Some common use cases include:
- **Mathematical Problems** (e.g., factorial, Fibonacci series)
- **Tree and Graph Traversal** (e.g., binary search trees, directory traversal)
- **Backtracking Algorithms** (e.g., solving puzzles like the N-Queens problem)

---

### **Tail Recursion**
In Python, **tail recursion** is a special kind of recursion where the recursive call is the last operation performed before returning the result. This allows for optimization, as it doesn’t add a new frame to the call stack.

However, Python does not optimize tail recursion like some other languages (e.g., Lisp or Scheme). So, deep recursion could lead to a `RecursionError` due to a stack overflow.

#### **Example of Tail Recursion:**
```python
def factorial_tail(n, accumulator=1):
    if n == 1:
        return accumulator
    else:
        return factorial_tail(n-1, n*accumulator)
```

Here, `accumulator` accumulates the result, and the recursive call is the last operation, making it tail recursive.

---

### **Key Concepts in Recursion:**
1. **Base Case**: Prevents infinite recursion and is essential for stopping the recursion.
2. **Recursive Case**: The part where the function calls itself, making progress towards the base case.
3. **Stack Overflow**: Recursion requires memory for each function call, and if the recursion goes too deep (i.e., too many nested function calls), it may lead to a stack overflow or a `RecursionError`.
4. **Efficiency**: Some problems can be solved more efficiently using recursion, but others may benefit from iteration (e.g., Fibonacci sequence using dynamic programming to avoid recalculating the same values multiple times).

---

### **Practical Examples of Recursion**

#### **1. Fibonacci Sequence:**

The Fibonacci sequence is defined as:
- \( F(0) = 0 \)
- \( F(1) = 1 \)
- \( F(n) = F(n-1) + F(n-2) \) for \( n > 1 \)

##### **Recursive Implementation:**
```python
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n-1) + fibonacci(n-2)
```

##### **How it Works:**
To calculate `fibonacci(5)`:
- `fibonacci(5)` calls `fibonacci(4)` and `fibonacci(3)`.
- `fibonacci(4)` calls `fibonacci(3)` and `fibonacci(2)`.
- This continues until the base case (`fibonacci(0)` or `fibonacci(1)`) is reached.

##### **Performance Warning**:  
This naive implementation has an exponential time complexity \( O(2^n) \) because the same Fibonacci values are recalculated multiple times. This is inefficient for large `n`.

---

### **Memoization for Optimizing Recursion**
To optimize recursive solutions like Fibonacci, we use **memoization**, where previously calculated values are stored so they aren't recomputed.

#### **Example Using Memoization:**
```python
def fibonacci_memo(n, memo={}):
    if n <= 1:
        return n
    if n not in memo:
        memo[n] = fibonacci_memo(n-1, memo) + fibonacci_memo(n-2, memo)
    return memo[n]
```

This reduces the time complexity to \( O(n) \) by caching intermediate results.

---

### **Recursive Algorithms in Data Structures**

#### **2. Binary Search:**
Binary search is a classic example of recursion in algorithms, where the search space is halved with each recursive call.

```python
def binary_search(arr, target, low, high):
    if low > high:
        return -1
    mid = (low + high) // 2
    if arr[mid] == target:
        return mid
    elif arr[mid] < target:
        return binary_search(arr, target, mid+1, high)
    else:
        return binary_search(arr, target, low, mid-1)
```

---

### **Advantages of Recursion:**
1. **Simplicity**: Recursion can make code easier to write and understand for problems like tree traversal, sorting, and mathematical computations.
2. **Elegance**: It leads to concise, elegant solutions for problems that have self-similar structure (e.g., divide and conquer problems).
3. **State Preservation**: Recursion can be useful in scenarios where you need to preserve the state across function calls, especially in algorithms like backtracking and tree traversal.

---

### **Challenges of Recursion:**
1. **Performance Issues**: Recursive solutions may lead to performance bottlenecks if not optimized (e.g., the Fibonacci sequence without memoization).
2. **Stack Overflow**: Too deep recursion can cause Python’s recursion limit to be exceeded. This can be controlled with `sys.setrecursionlimit()`, but it's generally better to switch to an iterative solution if the recursion depth is too large.
3. **Harder to Debug**: Debugging recursive functions can be tricky because of the multiple nested calls.

---

### **Handling Recursion Limit in Python**

Python has a default recursion depth limit (usually around 1000). If you need to handle deep recursion, you can adjust the recursion depth using the `sys` module.

```python
import sys
sys.setrecursionlimit(1500)  # Increase recursion depth limit
```

**Note**: Be cautious when adjusting the recursion limit as it can lead to system instability if set too high.

---

### **Exercises to Master Recursion:**
1. **Factorial**: Implement the factorial function recursively.
2. **Sum of a List**: Write a recursive function to find the sum of all elements in a list.
3. **Fibonacci Sequence**: Write a recursive function to compute the nth Fibonacci number.
4. **Tower of Hanoi**: Solve the Tower of Hanoi problem recursively.
5. **Binary Search**: Implement binary search recursively.
6. **Palindrome Check**: Write a recursive function to check if a string is a palindrome.
7. **Reverse a String**:

 Write a recursive function to reverse a string.
8. **Print All Subsets of a Set**: Write a recursive function to print all subsets of a given set.

---

### **Conclusion**
By now, you should have a solid understanding of recursion in Python. You’ve learned how to:
- Write recursive functions for mathematical computations (e.g., factorial, Fibonacci).
- Optimize recursion with techniques like memoization.
- Apply recursion to real-world problems like binary search and tree traversal.


### Hackerrank Problems
1. [Error handling](https://www.hackerrank.com/domains/python?filters%5Bsubdomains%5D%5B%5D=errors-exceptions)
----------------------

<p align="center"> <a href="./Day12.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day14.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

---------------
