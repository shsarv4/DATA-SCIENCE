<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day09.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day11.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>


## **Day 10: Exception Handling and Error Handling in Python**

### **Objective**
By the end of Day 10, you will:
- Understand how to handle exceptions using `try`, `except`, `else`, and `finally` blocks.
- Learn about common exception types and how to catch them.
- Create custom exceptions for better error handling.
- Understand the importance of the `finally` block for cleanup.
- Gain insights into best practices for error handling.

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=4LKo6dlku7M&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=36&ab_channel=CodeWithHarry)**
2. **[Video 2](https://www.youtube.com/watch?v=4LKo6dlku7M&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=37&ab_channel=CodeWithHarry)**
---

### **1. What Are Exceptions?**

**Exceptions** are errors that occur during the execution of a program. When Python encounters an error, it raises an exception, which halts the normal flow of the program. Without exception handling, these errors will cause the program to crash.

---

### **2. Basic Syntax of Exception Handling**

In Python, exception handling is done using the `try` and `except` blocks.

#### **Syntax:**

```python
try:
    # Code that may raise an exception
    risky_code()
except SomeException as e:
    # Code that runs if an exception occurs
    print(f"An error occurred: {e}")
```

#### **Example:**

```python
try:
    x = 10 / 0  # Division by zero
except ZeroDivisionError as e:
    print(f"Error: {e}")
```

Output:
```
Error: division by zero
```

---

### **3. Multiple Except Blocks**

You can have multiple `except` blocks to handle different exceptions separately.

#### **Example:**

```python
try:
    x = int(input("Enter a number: "))
    y = 10 / x
except ValueError as e:
    print(f"Invalid input: {e}")
except ZeroDivisionError as e:
    print(f"Cannot divide by zero: {e}")
except Exception as e:
    print(f"Some other error occurred: {e}")
```

Here, if the user enters a non-integer value, a `ValueError` will be caught. If the user enters `0`, a `ZeroDivisionError` will occur. Any other errors will be caught by the generic `Exception`.

---

### **4. Else Block**

An `else` block can be added after the `except` block. The code inside the `else` block will run only if no exceptions were raised in the `try` block.

#### **Syntax:**

```python
try:
    # Code that may raise an exception
except SomeException as e:
    # Code that runs if an exception occurs
else:
    # Code that runs if no exception occurs
```

#### **Example:**

```python
try:
    x = 10 / 2
except ZeroDivisionError:
    print("Cannot divide by zero!")
else:
    print("Division successful!")
```

Output:
```
Division successful!
```

---

### **5. Finally Block**

The `finally` block is used to define clean-up actions that must always be executed, whether an exception occurred or not. This is useful for releasing resources, closing files, or making sure specific tasks happen no matter what.

#### **Syntax:**

```python
try:
    # Code that may raise an exception
except SomeException as e:
    # Code that runs if an exception occurs
finally:
    # Code that runs no matter what
```

#### **Example:**

```python
try:
    x = 10 / 2
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("This will always run.")
```

Output:
```
This will always run.
```

The `finally` block is guaranteed to execute, even if there was an exception in the `try` block.

---

### **6. Common Python Exceptions**

Python has a variety of built-in exceptions that can be caught and handled. Some common ones include:

- `ZeroDivisionError`: Raised when a division by zero is attempted.
- `FileNotFoundError`: Raised when a file is not found.
- `ValueError`: Raised when a function receives an argument of the correct type but an inappropriate value.
- `TypeError`: Raised when an operation or function is applied to an object of inappropriate type.
- `IndexError`: Raised when a sequence subscript is out of range.
- `KeyError`: Raised when a dictionary key is not found.

---

### **7. Custom Exceptions**

In addition to built-in exceptions, you can define your own custom exceptions to handle specific errors in your application.

#### **Syntax for Custom Exception:**

You create a custom exception by inheriting from the base `Exception` class (or any other exception class).

```python
class CustomError(Exception):
    """Custom exception for specific errors."""
    def __init__(self, message):
        self.message = message
        super().__init__(self.message)
```

#### **Using Custom Exception:**

```python
class NegativeNumberError(Exception):
    """Raised when the input number is negative."""
    def __init__(self, message="Number cannot be negative"):
        self.message = message
        super().__init__(self.message)

def check_positive(number):
    if number < 0:
        raise NegativeNumberError(f"{number} is negative!")
    else:
        return number

try:
    check_positive(-5)
except NegativeNumberError as e:
    print(f"Caught error: {e}")
```

Output:
```
Caught error: -5 is negative!
```

Custom exceptions allow you to provide more meaningful error messages and handle specific error cases.

---

### **8. Raising Exceptions**

You can raise exceptions manually using the `raise` keyword. This is useful when you want to enforce certain conditions in your code.

#### **Syntax:**

```python
raise SomeException("Error message")
```

#### **Example:**

```python
def positive_check(x):
    if x < 0:
        raise ValueError("Value must be positive")
    return x

try:
    positive_check(-3)
except ValueError as e:
    print(f"Error: {e}")
```

Output:
```
Error: Value must be positive
```

---

### **9. Chaining Exceptions**

You can chain exceptions to raise a new exception while preserving the original exception. This is done using the `from` keyword.

#### **Syntax:**

```python
raise NewException("New error") from original_exception
```

#### **Example:**

```python
try:
    x = int("abc")  # Invalid conversion
except ValueError as e:
    raise ValueError("Invalid input for integer conversion") from e
```

Output:
```
ValueError: Invalid input for integer conversion
  Caused by: ValueError: invalid literal for int() with base 10: 'abc'
```

Chaining exceptions helps maintain context when handling errors.

---

### **10. Best Practices for Exception Handling**

1. **Use specific exceptions**: Always catch specific exceptions (e.g., `ValueError`, `TypeError`) rather than using the generic `except Exception` clause. This makes your code more robust and prevents hiding other potential issues.
   
2. **Log exceptions**: Always log the exception details (using `logging` module) for debugging purposes, especially in production environments.
   
3. **Avoid using exceptions for control flow**: Exceptions should be used for error handling, not for controlling the flow of your program. If you expect a condition to occur regularly, handle it through normal control flow (e.g., `if` statements).
   
4. **Clean up with `finally`**: Always use the `finally` block for clean-up tasks (e.g., closing files, network connections) to avoid resource leaks.

5. **Provide meaningful error messages**: Whether you use built-in or custom exceptions, make sure the error messages provide enough information for debugging.

---

### **Exercises:**

1. **Basic Exception Handling**: Write a program that accepts user input and divides 100 by the user input, handling `ZeroDivisionError` and `ValueError`.
   
2. **Custom Exceptions**: Create a custom exception `AgeError` that is raised when the entered age is less than 0 or greater than 150.

3. **Finally Block**: Write a program that reads from a file and prints the content. Ensure the file is always closed using a `finally` block.

4. **Chaining Exceptions**: Write a program that raises a `TypeError` due to invalid type conversion and chains it with a custom exception for invalid input.

---

### **Conclusion**

Today, you learned all about **exception handling** and **error handling** in Python. You explored:
- The basic structure of `try`, `except`, `else`, and `finally` blocks.
- How to handle multiple exceptions.
- The creation and use of custom exceptions.
- Best practices for robust and clean error handling.

### Hackerrank Problems
1. [Error handling](https://www.hackerrank.com/domains/python?filters%5Bsubdomains%5D%5B%5D=errors-exceptions)
----------------------

<p align="center"> <a href="./Day09.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day11.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

---------------
