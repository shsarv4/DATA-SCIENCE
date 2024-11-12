## **Day 4: Conditional Statements**

### **Objective**
By the end of Day 4, You, will understand how to use conditional statements (`if`, `elif`, and `else`) to make decisions in her Python programs. We’ll go over comparison and logical operators, nested conditions, and practical applications.

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=14)**

---
---

### **1. Theory**

#### **1.1 What are Conditional Statements?**

- **Conditional statements** allow us to execute code only when certain conditions are met. This makes programs flexible and interactive.
- The basic structure of a conditional statement includes `if`, `elif`, and `else` blocks.
  - **`if`**: Checks a condition and executes the block if the condition is true.
  - **`elif`** (optional): Checks additional conditions if previous conditions were false.
  - **`else`** (optional): Executes if none of the above conditions are met.

#### **1.2 The `if` Statement**

- The `if` statement is used to check a condition.
- **Syntax**:
  ```python
  if condition:
      # Code to execute if the condition is true
  ```

- **Example**:
  ```python
  age = 25
  if age >= 18:
      print("Swati is eligible to vote.")
  ```

#### **1.3 The `if-else` Statement**

- We use `else` to define an alternate block that runs if the `if` condition is false.
- **Syntax**:
  ```python
  if condition:
      # Code to execute if the condition is true
  else:
      # Code to execute if the condition is false
  ```

- **Example**:
  ```python
  age = 16
  if age >= 18:
      print("Swati is eligible to vote.")
  else:
      print("Swati is not eligible to vote.")
  ```

#### **1.4 The `if-elif-else` Statement**

- Use `elif` for additional conditions, allowing for multiple checks.
- **Syntax**:
  ```python
  if condition1:
      # Code if condition1 is true
  elif condition2:
      # Code if condition2 is true
  else:
      # Code if none of the conditions above are true
  ```

- **Example**:
  ```python
  marks = 75
  if marks >= 90:
      grade = "A"
  elif marks >= 75:
      grade = "B"
  else:
      grade = "C"
  print(f"Swati's grade is: {grade}")
  ```

#### **1.5 Comparison Operators**

Comparison operators are used to compare values, returning `True` or `False`.

- **Operators**:
  - `==`: Equal to
  - `!=`: Not equal to
  - `<`: Less than
  - `>`: Greater than
  - `<=`: Less than or equal to
  - `>=`: Greater than or equal to

- **Example**:
  ```python
  print(10 == 10)  # Output: True
  print(5 < 3)     # Output: False
  ```

#### **1.6 Logical Operators**

Logical operators allow combining multiple conditions.

- **Operators**:
  - **`and`**: Returns `True` if both conditions are true.
  - **`or`**: Returns `True` if at least one condition is true.
  - **`not`**: Inverts the truth value.

- **Example**:
  ```python
  age = 20
  is_student = True

  # Using 'and'
  if age >= 18 and is_student:
      print("Swati is an adult student.")

  # Using 'or'
  if age < 18 or is_student:
      print("Swati is either under 18 or a student.")
  
  # Using 'not'
  if not age < 18:
      print("Swati is not under 18.")
  ```

---

### **2. Practical Examples**

Let’s work through some examples Swati can relate to:

#### **2.1 Checking Eligibility for Different Activities**

1. **Voting Eligibility**:
   ```python
   age = 17
   if age >= 18:
       print("Swati is eligible to vote.")
   else:
       print("Swati is not eligible to vote.")
   ```

2. **Grading System**:
   - Using a more detailed grading system.
   ```python
   marks = 85
   if marks >= 90:
       grade = "A"
   elif marks >= 80:
       grade = "B"
   elif marks >= 70:
       grade = "C"
   else:
       grade = "D"
   print(f"Swati's grade is: {grade}")
   ```

3. **Weather-Based Outfit**:
   ```python
   temperature = 30  # in Celsius
   if temperature > 25:
       outfit = "T-shirt and shorts"
   elif temperature > 15:
       outfit = "Sweater and jeans"
   else:
       outfit = "Jacket and scarf"
   print(f"Swati should wear: {outfit}")
   ```

#### **2.2 Combining Conditions with Logical Operators**

1. **Gym Access**:
   - Only allow access if Swati is both an adult and a member.
   ```python
   age = 20
   is_member = True
   if age >= 18 and is_member:
       print("Swati can access the gym.")
   else:
       print("Access denied.")
   ```

2. **Discount Eligibility**:
   - Swati can get a discount if she is either a student or a senior.
   ```python
   is_student = True
   age = 25
   if is_student or age >= 60:
       print("Swati is eligible for a discount.")
   else:
       print("Swati is not eligible for a discount.")
   ```

#### **2.3 Nested Conditions**

Sometimes, conditions depend on other conditions. These are called **nested conditions**.

- **Example**: Checking if Swati can enter an event based on age and ticket status.
  ```python
  age = 22
  has_ticket = True

  if age >= 18:
      if has_ticket:
          print("Swati can enter the event.")
      else:
          print("Swati needs a ticket to enter.")
  else:
      print("Swati is too young to enter the event.")
  ```

---

### **3. Hands-On Practice Exercises**

These exercises will help Swati practice writing conditional statements and improve her logic-building skills.

1. **Exercise: Age Group Checker**
   - Write a program that checks if a person’s age is:
     - Under 13 (Child)
     - Between 13 and 19 (Teenager)
     - 20 or older (Adult)
   - Example:
     ```python
     age = 18
     if age < 13:
         print("Child")
     elif age <= 19:
         print("Teenager")
     else:
         print("Adult")
     ```

2. **Exercise: Price Calculator**
   - Write a program that applies a discount based on the amount spent:
     - If the amount is over 500, apply a 20% discount.
     - If it’s over 200, apply a 10% discount.
     - Otherwise, no discount.
   - Example:
     ```python
     amount = 300
     if amount > 500:
         discount = 0.2
     elif amount > 200:
         discount = 0.1
     else:
         discount = 0
     final_price = amount * (1 - discount)
     print("Final price:", final_price)
     ```

3. **Exercise: Pass or Fail**
   - Write a program that takes a student’s marks in three subjects. If the average is 40 or more and each subject is 33 or more, print "Pass". Otherwise, print "Fail".
   - Example:
     ```python
     marks1 = 45
     marks2 = 55
     marks3 = 50
     average = (marks1 + marks2 + marks3) / 3
     if average >= 40 and marks1 >= 33 and marks2 >= 33 and marks3 >= 33:
         print("Pass")
     else:
         print("Fail")
     ```

4. **Exercise: Even or Odd**
   - Write a program to check if a given number is even or odd.
   ```python
   number = 10
   if number % 2 == 0:
       print("Even")
   else:
       print("Odd")
   ```

5. **Exercise: Simple Calculator**
   - Write a basic calculator program that takes two numbers and an operator (`+`, `-`, `*`, `/`) as input, and performs the corresponding operation.
   - Example:
     ```python
     num1 = 15
     num2 = 5
     operator = "+"
     if operator == "+":
         result = num1 + num2
     elif operator == "-":
         result = num1 - num2
     elif operator == "*":
         result = num1 * num2
     elif operator == "/":
         result = num1 / num2
     print("Result:", result)
     ```

---


### **Shorthand Notation for Conditional Statements**

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

#### **Advanced Conditional Techniques**

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

#### **Advanced Conditional Expressions**

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


### **4. Challenge Problems**

1. **Leap Year Checker**:


   - Write a program to check if a given year is a leap year.
   - **Hint**: A leap year is divisible by 4 but not by 100, except if it’s also divisible by 400.
   ```python
   year = 2024
   if (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0):
       print("Leap year")
   else:
       print("Not a leap year")
   ```

2. **Temperature Alert**:
   - Write a program that takes a temperature in Celsius and prints:
     - "Cold" if below 10
     - "Warm" if between 10 and 25
     - "Hot" if above 25
   ```python
   temperature = 18
   if temperature < 10:
       print("Cold")
   elif temperature <= 25:
       print("Warm")
   else:
       print("Hot")
   ```

---


### **5. Wrap-Up: Review and Reflection**

By the end of today, you should feel comfortable using conditional statements and should understand how they allow for flexible, decision-based programming.

#### **Reflection Questions**
1. Why are conditional statements important in programming?
2. How does the `elif` statement make your code more efficient?
3. How would you use logical operators to combine multiple conditions?

#### **Recap Quiz**
1. What’s the difference between `if`, `elif`, and `else`?
2. How can you check if two conditions are both true?
3. Write a simple example of nested conditionals.

### Hackerrank Problems
1. **[]()**

#### [Prev](./Day03.md) ___ [Next](./Day05.md)
