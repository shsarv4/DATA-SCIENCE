## **Day 5: Loops, Break, and Continue**

### **Objective**
By the end of Day 5, You will be able to use loops to repeat tasks, understand how to control loop execution with `break` and `continue`, and apply loops in various real-world scenarios.


### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=17)**
2. **[Video 2](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=18)**
3. **[Video 3](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=19)**
---

### **1. Theory**

#### **1.1 What are Loops?**

- **Loops** allow repeating a block of code multiple times. They are essential for tasks like processing items in a list, calculating sums, or performing actions until a condition is met.
- Python has two main types of loops:
  - **`for` loop**: Used to iterate over a sequence (like a list, tuple, dictionary, or string).
  - **`while` loop**: Continues as long as a specified condition is `True`.

#### **1.2 The `for` Loop**

- **Syntax**:
  ```python
  for item in sequence:
      # Code to execute for each item
  ```
- **Example**: Using a `for` loop to print each item in a list.
  ```python
  hobbies = ["painting", "reading", "coding"]
  for hobby in hobbies:
      print(hobby)
  ```

#### **1.3 The `while` Loop**

- **Syntax**:
  ```python
  while condition:
      # Code to execute while the condition is true
  ```
- **Example**: A `while` loop to print numbers from 1 to 5.
  ```python
  count = 1
  while count <= 5:
      print(count)
      count += 1
  ```

- **When to Use `for` vs `while` Loops**:
  - Use a `for` loop when you know the number of iterations or are looping through a specific collection (e.g., list, tuple).
  - Use a `while` loop when the number of iterations isn’t fixed, and you want to continue until a condition is met.

#### **1.4 The `range()` Function**

- The `range()` function generates a sequence of numbers, commonly used in `for` loops.
  - **Syntax**:
    ```python
    range(start, stop, step)
    ```
  - `start` (optional): The number to start from (default is `0`).
  - `stop`: The number to stop at (this number is not included).
  - `step` (optional): The increment (default is `1`).

- **Example**:
  ```python
  for i in range(5):
      print(i)  # Outputs 0, 1, 2, 3, 4
  ```

#### **1.5 `break` and `continue` Statements**

- **`break`**: Exits the loop when a certain condition is met.
  - **Example**:
    ```python
    for number in range(10):
        if number == 5:
            break
        print(number)
    # Output: 0, 1, 2, 3, 4
    ```

- **`continue`**: Skips the current iteration and moves to the next.
  - **Example**:
    ```python
    for number in range(10):
        if number == 5:
            continue
        print(number)
    # Output: 0, 1, 2, 3, 4, 6, 7, 8, 9
    ```

#### **1.6 Nested Loops**

- **Nested loops** are loops inside another loop, commonly used for multi-dimensional data (like rows and columns).
- **Example**:
  ```python
  for i in range(3):
      for j in range(2):
          print(f"i: {i}, j: {j}")
  ```

---

### ** Looping Through Various Data Structures**  

<h3 align="center">We Will Learn about Each data Structure Later<h3>

#### **Looping Through Lists:**

```python
numbers = [1, 2, 3, 4]
for num in numbers:
    print(num)
```

#### **Looping Through a String:**

```python
text = "hello"
for char in text:
    print(char)
```

#### **Looping Through a Dictionary:**

```python
person = {"name": "Alice", "age": 25}
for key, value in person.items():
    print(f"{key}: {value}")
```

Output:
```
name: Alice
age: 25
```

----

### **2. Practical Examples**

Let’s go through some practical loop examples Swati can relate to:

#### **2.1 Using a `for` Loop to Greet Friends**

```python
friends = ["Amit", "Neha", "Rohan"]
for friend in friends:
    print(f"Hello, {friend}!")
```

#### **2.2 Sum of Numbers Using a `for` Loop**

- Calculate the sum of the first 10 natural numbers.
  ```python
  total = 0
  for num in range(1, 11):
      total += num
  print("Sum of first 10 natural numbers:", total)
  ```

#### **2.3 Counting Down with a `while` Loop**

- Use a `while` loop to create a countdown timer from 5 to 1.
  ```python
  count = 5
  while count > 0:
      print(count)
      count -= 1
  print("Liftoff!")
  ```

#### **2.4 Skipping Odd Numbers with `continue`**

- Print only even numbers between 1 and 10.
  ```python
  for num in range(1, 11):
      if num % 2 != 0:
          continue
      print(num)
  ```

#### **2.5 Breaking Out of a Loop When a Condition is Met**

- Find and print the first number greater than 15 in a list.
  ```python
  numbers = [10, 12, 14, 18, 20]
  for num in numbers:
      if num > 15:
          print("First number greater than 15:", num)
          break
  ```

#### **2.6 Nested Loops for Multiplication Table**

- Generate a multiplication table (1-3).
  ```python
  for i in range(1, 4):
      for j in range(1, 4):
          print(f"{i} x {j} = {i * j}")
  ```

---

### **3. Hands-On Practice Exercises**

These exercises will help Swati build confidence with loops by practicing different scenarios.

1. **Exercise: Print Each Character in a String**
   - Use a `for` loop to print each character in Swati’s name individually.
   - Example:
     ```python
     name = "Swati"
     for char in name:
         print(char)
     ```

2. **Exercise: Countdown Timer**
   - Write a `while` loop to print a countdown from 10 to 1, then print "Happy New Year!".
   ```python
   count = 10
   while count > 0:
       print(count)
       count -= 1
   print("Happy New Year!")
   ```

3. **Exercise: Sum of Even Numbers**
   - Use a `for` loop to find the sum of all even numbers from 1 to 20.
   ```python
   total = 0
   for num in range(1, 21):
       if num % 2 == 0:
           total += num
   print("Sum of even numbers from 1 to 20:", total)
   ```

4. **Exercise: Skip Multiples of 3**
   - Write a loop that prints numbers from 1 to 20, but skip numbers that are multiples of 3.
   ```python
   for num in range(1, 21):
       if num % 3 == 0:
           continue
       print(num)
   ```

5. **Exercise: Simple Password Checker**
   - Ask the user to enter a password and keep asking until they enter the correct password (`"python123"`). Use a `while` loop to accomplish this.
   ```python
   password = ""
   while password != "python123":
       password = input("Enter the password: ")
   print("Access granted!")
   ```

---

### **4. Challenge Problems**

1. **FizzBuzz**
   - Write a program that prints numbers from 1 to 50. For multiples of 3, print "Fizz" instead of the number. For multiples of 5, print "Buzz". For multiples of both 3 and 5, print "FizzBuzz".
   ```python
   for num in range(1, 51):
       if num % 3 == 0 and num % 5 == 0:
           print("FizzBuzz")
       elif num % 3 == 0:
           print("Fizz")
       elif num % 5 == 0:
           print("Buzz")
       else:
           print(num)
   ```

2. **Prime Number Checker (Using a Loop)**
   - Write a program that checks if a given number is prime.
   - **Hint**: A prime number has no divisors other than 1 and itself.
   ```python
   number = 29
   is_prime = True
   for i in range(2, int(number ** 0.5) + 1):
       if number % i == 0:
           is_prime = False
           break
   if is_prime:
       print(f"{number} is a prime number.")
   else:
       print(f"{number} is not a prime number.")
   ```

3. **Finding the Largest Number**
   - Given a list of numbers, use a loop to find and print the largest number in the list.
   ```python
   numbers = [3, 8, 2, 7, 9, 4]
   largest = numbers[0]
   for num in numbers:
       if num> largest:
           largest = num
   print("The largest number is:", largest)
   ```

---


### **5. Wrap-Up: Review and Reflection**

By the end of today, you should be comfortable using loops to repeat tasks, understand the role of `break` and `continue`, and know when to use `for` and `while` loops.

#### **Reflection Questions**
1. What’s the difference between a `for` loop and a `while` loop?
2. How do `break` and `continue` affect loop flow?
3. How would you use a nested loop in a real-world example?

#### **Recap Quiz**
1. What does the `range()` function do?
2. Write an example where you use `continue` to skip even numbers.
3. How do you stop a loop from executing once a certain condition is met?

---

### Hackerrank Problems
1. **[]()**

#### [Prev](./PYTHON/Day04.md) ___ [Next](./PYTHON/Day06.md)
