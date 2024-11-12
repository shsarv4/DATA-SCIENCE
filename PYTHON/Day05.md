## **Day 6: Functions, Arguments, and Lambda Functions**

### **Objective**
By the end of Day 6, You will understand how to create and use functions, work with different types of arguments, and use lambda functions for concise operations.

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=20)**
2.  **[Video 1](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=21)**
---

### **1. Theory**

#### **1.1 What is a Function?**

- **Functions** are reusable blocks of code that perform a specific task. Functions help organize code, improve readability, and allow us to avoid repeating code.
- Functions are defined using the `def` keyword, followed by the function name, parentheses `()`, and a colon `:`. The code inside the function is indented.
  
- **Syntax**:
  ```python
  def function_name():
      # Code to execute
  ```

#### **1.2 Creating and Calling a Function**

- **Creating a Function**:
  - Define a function using `def`, give it a name, and place any code you want it to execute inside.
  
- **Calling a Function**:
  - To execute a function, simply call it by its name followed by parentheses `()`.
  
- **Example**:
  ```python
  def greet():
      print("Hello, Swati!")

  # Calling the function
  greet()
  ```

#### **1.3 Function with Parameters**

- **Parameters** allow us to pass information into a function so it can perform tasks based on different inputs.
- **Syntax**:
  ```python
  def function_name(parameter1, parameter2):
      # Code using parameter1 and parameter2
  ```
  
- **Example**:
  ```python
  def greet(name):
      print(f"Hello, {name}!")

  greet("Swati")  # Output: Hello, Swati!
  ```

#### **1.4 Function with Return Statement**

- **`return`** is used to send a value back to the caller of the function. This allows the function to output data that can be stored or used later.
- **Syntax**:
  ```python
  def function_name(parameter):
      # Code
      return value
  ```

- **Example**:
  ```python
  def add(a, b):
      return a + b

  result = add(5, 3)
  print(result)  # Output: 8
  ```

#### **1.5 Function Arguments**

Python supports several types of arguments in functions:

1. **Positional Arguments**:
   - Passed in the same order as defined in the function.
   ```python
   def describe(name, age):
       print(f"{name} is {age} years old.")

   describe("Swati", 25)  # Output: Swati is 25 years old.
   ```

2. **Keyword Arguments**:
   - Allows passing arguments by explicitly naming each parameter.
   ```python
   describe(age=25, name="Swati")  # Output: Swati is 25 years old.
   ```

3. **Default Arguments**:
   - Assign a default value to a parameter, used if no argument is provided.
   ```python
   def greet(name="Guest"):
       print(f"Hello, {name}!")

   greet()            # Output: Hello, Guest!
   greet("Swati")     # Output: Hello, Swati!
   ```

4. **Variable-Length Arguments**:
   - **`*args`**: Allows passing a variable number of positional arguments.
     ```python
     def add_numbers(*args):
         total = sum(args)
         print("Sum:", total)

     add_numbers(3, 5, 7)  # Output: Sum: 15
     ```
   - **`**kwargs`**: Allows passing a variable number of keyword arguments.
     ```python
     def display_info(**kwargs):
         for key, value in kwargs.items():
             print(f"{key}: {value}")

     display_info(name="Swati", age=25, city="Bhopal")
     # Output:
     # name: Swati
     # age: 25
     # city: Bhopal
     ```

---

### **2. Practical Examples**

Let’s go through some examples where Swati might use functions in real-world scenarios.

#### **2.1 Function to Calculate Area of a Circle**

```python
def calculate_area(radius):
    area = 3.14159 * radius ** 2
    return area

print("Area of circle:", calculate_area(5))  # Output: Area of circle: 78.53975
```

#### **2.2 Function with Default Arguments**

```python
def introduce(name, hobby="painting"):
    print(f"My name is {name}, and I love {hobby}.")

introduce("Swati")                    # Output: My name is Swati, and I love painting.
introduce("Swati", "coding")          # Output: My name is Swati, and I love coding.
```

#### **2.3 Variable-Length Arguments with `*args`**

```python
def favorite_foods(*foods):
    print("Swati's favorite foods are:")
    for food in foods:
        print(food)

favorite_foods("Pizza", "Pasta", "Sushi")
```

#### **2.4 Function with `**kwargs` for Multiple Details**

```python
def display_profile(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

display_profile(name="Swati", age=25, city="Bhopal", profession="Engineer")
```

---

### **3. Lambda Functions**

#### **3.1 What is a Lambda Function?**

- **Lambda functions** are anonymous, single-line functions typically used for simple operations.
- They are defined using the `lambda` keyword, followed by parameters, a colon, and an expression.

- **Syntax**:
  ```python
  lambda arguments: expression
  ```

#### **3.2 Using Lambda Functions**

1. **Basic Lambda Function**:
   ```python
   add = lambda x, y: x + y
   print(add(3, 5))  # Output: 8
   ```

2. **Lambda with `map()`**:
   - `map()` applies a function to every item in an iterable.
   ```python
   numbers = [1, 2, 3, 4]
   squared = list(map(lambda x: x ** 2, numbers))
   print(squared)  # Output: [1, 4, 9, 16]
   ```

3. **Lambda with `filter()`**:
   - `filter()` filters items in an iterable based on a function’s condition.
   ```python
   numbers = [5, 10, 15, 20, 25]
   filtered = list(filter(lambda x: x > 15, numbers))
   print(filtered)  # Output: [20, 25]
   ```

4. **Lambda with `sorted()`**:
   - `sorted()` can use a lambda function to define a custom sort order.
   ```python
   words = ["apple", "banana", "kiwi", "cherry"]
   sorted_words = sorted(words, key=lambda word: len(word))
   print(sorted_words)  # Output: ['kiwi', 'apple', 'banana', 'cherry']
   ```

---

### **4. Hands-On Practice Exercises**

These exercises will reinforce Swati’s understanding of functions, arguments, and lambda expressions.

1. **Exercise: Temperature Converter**
   - Write a function that converts Celsius to Fahrenheit. Use the formula `F = C * 9/5 + 32`.
   ```python
   def celsius_to_fahrenheit(celsius):
       return celsius * 9/5 + 32

   print(celsius_to_fahrenheit(25))  # Output: 77.0
   ```

2. **Exercise: Personalized Greeting**
   - Write a function that takes a name and age, then prints a personalized greeting.
   ```python
   def greet(name, age):
       print(f"Hello, {name}! You are {age} years old.")

   greet("Swati", 25)
   ```

3. **Exercise: Sum of Unknown Numbers**
   - Write a function using `*args` that calculates the sum of an unknown number of arguments.
   ```python
   def sum_numbers(*args):
       return sum(args)

   print(sum_numbers(1, 2, 3, 4))  # Output: 10
   ```

4. **Exercise: Simple Calculator Using Lambdas**
   - Create a lambda function for each basic operation (`add`, `subtract`, `multiply`, `divide`).
   ```python
   add = lambda x, y: x + y
   subtract = lambda x, y: x - y
   multiply = lambda x, y: x * y
   divide = lambda x, y: x / y if y != 0 else "Cannot divide by zero"

   print(add(10, 5))           # Output: 15
   print(subtract(10, 5))      # Output: 5
   print(multiply(10, 5))      # Output: 50
   print(divide(10, 0))        # Output: Cannot divide by zero
   ```

5. **Exercise: Filtering Odd Numbers**
   - Use `filter()` and a lambda function to filter out only odd numbers from a list.
   ```python
   numbers = [1, 2, 

3, 4, 5, 6, 7, 8, 9, 10]
   odd_numbers = list(filter(lambda x: x % 2 != 0, numbers))
   print(odd_numbers)  # Output: [1, 3, 5, 7, 9]
   ```

---

### **5. Challenge Problems**

1. **Factorial Function (Using Recursion)**
   - Write a function that calculates the factorial of a number using recursion.
   ```python
   def factorial(n):
       if n == 0:
           return 1
       else:
           return n * factorial(n - 1)

   print(factorial(5))  # Output: 120
   ```

2. **Lambda for Sorting Complex Data**
   - Given a list of tuples representing products (`name`, `price`), use `sorted()` with a lambda to sort by price.
   ```python
   products = [("Laptop", 900), ("Phone", 600), ("Tablet", 300)]
   sorted_products = sorted(products, key=lambda item: item[1])
   print(sorted_products)
   ```

3. **Count Vowels in a String**
   - Write a function that counts the number of vowels in a given string.
   ```python
   def count_vowels(s):
       return len(list(filter(lambda x: x.lower() in "aeiou", s)))

   print(count_vowels("Hello Swati"))  # Output: 4
   ```

---

### **6. Wrap-Up: Review and Reflection**

By the end of today, YOu should feel comfortable with defining and calling functions, using different types of arguments, and leveraging lambda functions.

#### **Reflection Questions**
1. Why are functions important in programming?
2. When would you use `*args` and `**kwargs`?
3. How do lambda functions differ from regular functions?

#### **Recap Quiz**
1. What does `return` do in a function?
2. Write a lambda function to find the square of a number.
3. How do you define a function with default arguments?

---

### Hackerrank Problems
1. **[]()**

#### [Prev](./Day05.md) ___ [Next](./Day07.md)
