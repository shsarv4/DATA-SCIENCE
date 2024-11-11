## **Day 2: Variables and Data Types**

### **Objective**
By the end of Day 2, Swati, you will understand variables, how to use them effectively, and become familiar with Python’s basic data types. Today’s session will go deep into how variables work, how Python handles data, and practical applications that connect with her daily life.


#### Video Links

1. [https://www.youtube.com/watch?v=ORCuz7s5cCY&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=6](https://www.youtube.com/watch?v=ORCuz7s5cCY&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=6)
2. [https://www.youtube.com/watch?v=Pu5bqySSSS0&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=9](https://www.youtube.com/watch?v=Pu5bqySSSS0&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=9)
3. [https://www.youtube.com/watch?v=WvG-R-xXouA&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=10](https://www.youtube.com/watch?v=WvG-R-xXouA&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=10)
---


### **1. Theory**

#### **1.1 Understanding Variables**

- **What is a Variable?**
  - A variable in Python is a named location used to store data in memory. Think of it as a labeled container where you can keep data (like numbers, text, or even lists of items) and access it later using the variable name.
  - Variables allow us to work flexibly with information in a program, as they can change values as needed.
  - **Example**: Imagine Swati wants to store her age, favorite color, and name in a program. She can use variables like `age`, `favorite_color`, and `name` to store these details.

- **Creating Variables in Python**
  - In Python, a variable is created by simply assigning it a value using the `=` operator:
    ```python
    age = 25           # Integer
    name = "Swati"     # String
    favorite_color = "Blue"  # String
    is_student = True  # Boolean
    ```

- **Naming Rules for Variables**:
  - Start with a letter or underscore (_), but not with a number.
  - Avoid spaces; instead, use underscores (e.g., `favorite_color`).
  - Avoid using reserved words like `if`, `while`, `print`, etc.

#### **1.2 Python Data Types**

Understanding data types is essential for working effectively in Python. Here are some fundamental types and how to use them:

- **Integer**: Used for whole numbers (e.g., `25`, `2023`).
  ```python
  age = 25
  year = 2023
  ```
  
- **Float**: Used for decimal numbers (e.g., `3.14`, `98.6`).
  ```python
  temperature = 98.6
  height = 5.4
  ```

- **String**: Text data, represented inside quotes (single or double quotes).
  ```python
  name = "Swati"
  favorite_quote = "The journey of learning is never-ending."
  ```

- **Boolean**: Represents a true/false value, useful for conditions and control flow.
  ```python
  is_student = True
  is_raining = False
  ```

#### **1.3 Checking Data Types**

- Python provides the `type()` function to check a variable's type.
  ```python
  print(type(age))         # Output: <class 'int'>
  print(type(favorite_color)) # Output: <class 'str'>
  print(type(is_student))   # Output: <class 'bool'>
  ```

---

### **2. Practical Examples**

Let’s work with these data types in practical, everyday examples that Swati might enjoy.

#### **2.1 Creating and Displaying Variables**

1. **Using Personal Information**:
   ```python
   # Swati's details
   name = "Swati"
   age = 25
   favorite_hobby = "painting"
   
   print("Name:", name)
   print("Age:", age)
   print("Hobby:", favorite_hobby)
   ```

2. **Updating a Variable**:
   - Variables can be reassigned new values.
   ```python
   favorite_color = "Blue"
   print("Favorite color:", favorite_color)  # Output: Blue

   # Swati changes her favorite color
   favorite_color = "Green"
   print("Updated favorite color:", favorite_color)  # Output: Green
   ```

3. **Concatenating Strings**:
   - Swati can combine different pieces of information in a sentence.
   ```python
   greeting = "Hello, my name is " + name + ". I'm " + str(age) + " years old."
   print(greeting)
   ```

4. **Basic Arithmetic with Variables**:
   - Swati can perform arithmetic operations with integer and float variables.
   ```python
   base = 5
   height = 10
   area_of_triangle = 0.5 * base * height
   print("The area of the triangle is:", area_of_triangle)
   ```

#### **2.2 Exploring Data Types with the `type()` Function**

1. **Checking Types of Variables**:
   ```python
   print("Type of age:", type(age))                 # Output: <class 'int'>
   print("Type of favorite_color:", type(favorite_color)) # Output: <class 'str'>
   print("Type of is_student:", type(is_student))   # Output: <class 'bool'>
   ```

2. **Type Conversion**:
   - Convert one data type to another when needed.
   ```python
   height = "5.6"  # Initially a string
   height = float(height)  # Convert to float for mathematical calculations
   print("Updated height:", height)  # Output: 5.6
   ```

---

### **3. Practical Exercises**

These exercises will help Swati apply what she’s learned today.

1. **Exercise: Personal Details**
   - Write a script that creates variables for your name, favorite hobby, and favorite book. Then, print each detail in a separate line, followed by the data type of each variable.
   - Example output:
     ```plaintext
     Name: Swati
     Favorite hobby: Painting
     Favorite book: "To Kill a Mockingbird"
     ```

2. **Exercise: Age Calculation**
   - Define your current age and then calculate how old you’ll be in 5, 10, and 20 years. Print each result.
   - Example:
     ```python
     current_age = 25
     print("In 5 years:", current_age + 5)
     print("In 10 years:", current_age + 10)
     print("In 20 years:", current_age + 20)
     ```

3. **Exercise: Arithmetic Operations**
   - Define two variables, `num1` and `num2`, and perform addition, subtraction, multiplication, and division with them. Print the result of each operation.
   - Example:
     ```python
     num1 = 8
     num2 = 3
     print("Addition:", num1 + num2)
     print("Subtraction:", num1 - num2)
     print("Multiplication:", num1 * num2)
     print("Division:", num1 / num2)
     ```

4. **Exercise: Changing Variable Types**
   - Take a string variable for a height (e.g., `"5.8"`), convert it to a float, and then print it with an appropriate message.
   - Example:
     ```python
     height = "5.8"
     height = float(height)
     print("Swati's height is:", height)
     ```

5. **Exercise: Experiment with `print()` and Types**
   - Write a script that includes:
     - A line that prints multiple types (string, integer, boolean) in a single `print()` call.
     - Use the `type()` function within the print statements to display each variable’s type.
   - Example:
     ```python
     name = "Swati"
     age = 25
     is_student = True
     
     print("Name:", name, "- Type:", type(name))
     print("Age:", age, "- Type:", type(age))
     print("Is student:", is_student, "- Type:", type(is_student))
     ```

---

### **4. Challenge Problems**

For a bit of extra practice, here are some more challenging problems.

1. **Temperature Conversion**:
   - Create a variable for a temperature in Celsius (e.g., `celsius = 25`), convert it to Fahrenheit using the formula `(Celsius * 9/5) + 32`, and print the result.
  
2. **String Interpolation**:
   - Use an `f-string` (formatted string) to output the following message:
     ```plaintext
     "Swati's favorite color is Blue, and her current age is 25."
     ```

3. **More on Arithmetic**:
   - Given `num1 = 12` and `num2 = 5`, find and print:
     - The modulus (remainder when `num1` is divided by `num2`)
     - The result of `num1` raised to the power of `num2`

---

### **5. Wrap-Up: Review and Reflection**

By the end of today, Swati should be comfortable with the essentials of variables and data types, as well as how to display and manipulate these variables.

#### **Reflection Questions**
1. What’s the difference between a string, an integer, and a float?
2. Why is it helpful to check the data type of a variable?
3. How would you describe a Boolean variable and its purpose?

#### **Recap Quiz**
1. What data type would Python assign to the following values?
   - `"Hello, Swati!"`
   - `2023`
   - `True`
   - `3.14`
2. What happens if you add an integer and a float in Python? Try it out!

#### [Prev](./PYTHON/Day01.md) ___ [Next](./PYTHON/Day03.md)

