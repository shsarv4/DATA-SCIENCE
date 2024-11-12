## Day 3: Conditional Statements and Operations

### Objective
By the end of Day 4, you will have mastered the use of conditional statements and operations in Python. You'll learn how to:
- Use `if-else`, `elif`, and nested `if` statements
- Implement conditional expressions
- Understand and apply all operations (arithmetic, comparison, logical, assignment) in Python
- Work with shorthand notation for conditions in single lines

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=14)**

---

### Theory

#### 1. **Conditional Statements in Python**

Conditional statements are the backbone of decision-making in programming. They allow you to execute different code based on specific conditions.

##### **1.1 Syntax of Conditional Statements**
- **Basic `if` Statement**: Executes code when a condition is `True`.
  ```python
  if condition:
      # Code to execute
  ```

- **`if-else` Statement**: Executes one block if the condition is `True`, another if `False`.
  ```python
  if condition:
      # True block
  else:
      # False block
  ```

- **`if-elif-else` Statement**: Allows multiple conditions, executing the corresponding block for the first `True` condition.
  ```python
  if condition1:
      # Block 1
  elif condition2:
      # Block 2
  else:
      # Default block
  ```

- **Nested `if` Statements**: Using an `if` statement inside another `if` or `else` block.
  ```python
  if condition1:
      if condition2:
          # Nested block
      else:
          # Else block for condition1
  else:
      # Else block for condition1
  ```

---

#### **1.2 Shorthand Notation for Conditional Statements**

Python provides shorthand methods to simplify conditional logic, making it more compact and readable.

- **Ternary Operator** (Conditional Expression): A compact way to write `if-else` in a single line.
  ```python
  value_if_true if condition else value_if_false
  ```
  Example:
  ```python
  result = "Even" if x % 2 == 0 else "Odd"
  ```

- **Multiple Conditions with `and`, `or`, and `not`**:
  - **`and`**: Returns `True` if both conditions are `True`.
    ```python
    if x > 5 and x < 10:
        print("x is between 5 and 10")
    ```
  - **`or`**: Returns `True` if at least one condition is `True`.
    ```python
    if x == 5 or x == 10:
        print("x is either 5 or 10")
    ```
  - **`not`**: Reverses the condition.
    ```python
    if not x > 10:
        print("x is 10 or less")
    ```

- **Short-circuiting**: Python evaluates conditions from left to right, stopping as soon as the outcome is determined. This is useful when dealing with expensive operations.
  ```python
  if condition1 and expensive_operation():
      # Expensive operation is only called if condition1 is True
  ```

---

#### **1.3 Advanced Conditional Techniques**

- **Inline `if` with `and`/`or`**: Combine conditions into a single expression.
  ```python
  result = "Even" if x % 2 == 0 else "Odd" if x > 0 else "Negative Odd"
  ```

- **Short-circuit Evaluation with `and`/`or`**: Combine conditions and simplify nested logic.
  ```python
  print("x is positive and even" if x > 0 and x % 2 == 0 else "x is odd or negative")
  ```

- **Chained Comparison**: Multiple comparisons in a single expression.
  ```python
  if 1 < x < 10:
      print("x is between 1 and 10")
  ```

---

#### **1.4 Advanced Conditional Expressions**

- **The `all()` and `any()` Functions**: Check multiple conditions with `all()` (all conditions must be `True`) or `any()` (at least one condition must be `True`).
  ```python
  if all([x > 0, x < 10, x % 2 == 0]):
      print("x is positive, less than 10, and even")

  if any([x > 5, x == 5, x < 10]):
      print("x satisfies at least one condition")
  ```

- **Lambda Expressions in Conditions**: Use lambdas for inline conditional logic.
  ```python
  condition = lambda x: "Positive" if x > 0 else "Negative"
  print(condition(5))
  ```

---

#### 2. **Operations in Python**

Python supports a wide range of operations that can be applied to variables, data types, and objects.

##### **2.1 Arithmetic Operations**
- Addition: `a + b`
- Subtraction: `a - b`
- Multiplication: `a * b`
- Division: `a / b`
- Modulus (remainder): `a % b`
- Exponentiation: `a ** b`

##### **2.2 Comparison Operations**
Used to compare two values:
- Equal: `a == b`
- Not Equal: `a != b`
- Greater Than: `a > b`
- Less Than: `a < b`
- Greater Than or Equal: `a >= b`
- Less Than or Equal: `a <= b`

##### **2.3 Logical Operations**
- `and`: Combines two conditions, returns `True` if both are `True`.
- `or`: Combines two conditions, returns `True` if at least one is `True`.
- `not`: Reverses the result of a condition.

##### **2.4 Assignment Operations**
- Assign: `a = b`
- Add and Assign: `a += b`
- Subtract and Assign: `a -= b`
- Multiply and Assign: `a *= b`
- Divide and Assign: `a /= b`
- Modulus and Assign: `a %= b`

---

### Practical Examples

**Example 1: Using `if-else`**
```python
x = 10
result = "Greater than 5" if x > 5 else "Less than or equal to 5"
print(result)
```

**Example 2: Using `if-elif-else`**
```python
x = 10
result = "Greater than 5" if x > 5 else "Equal to 5" if x == 5 else "Less than 5"
print(result)
```

**Example 3: Using Nested `if-else`**
```python
x = 10
if x > 5:
    if x % 2 == 0:
        print("x is greater than 5 and even")
    else:
        print("x is greater than 5 and odd")
else:
    print("x is less than or equal to 5")
```

---

### Exercises

**Exercise 1: Conditional Statements**
- Write a script to check if a number is positive, negative, or zero using `if-elif-else` statements.

**Exercise 2: Shorthand Conditions**
- Write a script using a ternary operator to check if a number is divisible by 5.

**Exercise 3: Logical Operations**
- Write a script that checks if a number is positive and even using `and` and `not`.

**Exercise 4: Assignment Operations**
- Use assignment operators to calculate the final value of a variable after multiple operations.

---

### Challenge Problems

**Challenge 1: Create a "Guess the Number" Game**
- Generate a random number between 1 and 100.
- Let the user guess, and provide feedback (too high, too low, or correct).
- Continue until the user guesses correctly.

**Challenge 2: Build a Rock, Paper, Scissors Game**
- Allow the user to select Rock, Paper, or Scissors.
- Use conditional statements to determine if the user won, lost, or tied with the computer.

---

### Hackerrank Problems
1. **[]()**

#### [Prev](./PYTHON/Day03.md) ___ [Next](./PYTHON/Day05.md)
