<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center">
  <a href="./Day02.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a>
</p>

## **Day 1: Python Fundamentals, Installation, and Your First Program**

### **Objective**
By the end of Day 1, you’ll have installed Python, understand what Python is and why it's popular, and gain hands-on experience with basic commands and Python’s interactive interpreter. You’ll also start programming by writing and running simple scripts.

#### Video Links
1. [Video 1](https://www.youtube.com/watch?v=7wnove7K-ZQ&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg)
2. [Vidoes 2](https://www.youtube.com/watch?v=7IWOYhfAcVg&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=4)
3. [Vidoes 3](https://www.youtube.com/watch?v=qxPMmW93eDs&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=5)
---

### **1. Theory**

#### **1.1 Introduction to Python**

- **What is Python?**
  - Python is a high-level, interpreted programming language known for its readability and simplicity, making it ideal for both beginners and experienced developers. It’s used widely across many fields, including web development, data science, artificial intelligence, automation, and more.
  
- **Why Learn Python?**
  - **Readability**: Python’s syntax is clear and intuitive, often resembling plain English.
  - **Versatility**: Python supports multiple programming paradigms, including object-oriented, procedural, and functional programming.
  - **Rich Libraries**: It comes with a massive ecosystem of libraries for almost any task, from data analysis (`pandas`, `numpy`) to web development (`Flask`, `Django`), and more.
  - **Community Support**: Being one of the most popular languages, Python has vast documentation, tutorials, and a helpful community for support.

#### **1.2 Setting Up Python**

- **Download Python**:
  - Go to [python.org](https://www.python.org/downloads/) and download the latest stable release for your OS.
  - During installation, check the box to **Add Python to PATH** (important for command-line use).

- **Verifying the Installation**:
  - Open your command line (Command Prompt on Windows or Terminal on Mac/Linux).
  - Type `python --version` and press Enter. You should see a message showing the installed Python version (e.g., `Python 3.10.2`).

#### **1.3 Understanding the Python Interpreter and Scripts**

- **Python Interpreter**:
  - This is the interactive mode where you can type Python commands directly, and they execute immediately. To open the Python interpreter:
    ```shell
    python
    ```
  - You can test code snippets here quickly, but they won’t be saved.

- **Python Scripts**:
  - Scripts are files containing a sequence of Python commands. They allow you to save and reuse code. Scripts have a `.py` extension, like `my_script.py`.
  - To create and run a script:
    1. Open a text editor (e.g., Visual Studio Code, Sublime Text).
    2. Write code in the file, save it as `my_script.py`.
    3. In the command line, navigate to the script’s folder and run:
       ```shell
       python my_script.py
       ```

---

### **2. Practical Examples and Concepts**

#### **2.1 Running Your First Program**

- Open Python in interactive mode (type `python` in the terminal).
- Write your first line of code:
  ```python
  print("Hello, World!")
  ```
  - The `print()` function outputs text to the console. In this case, it outputs `Hello, World!`.

#### **2.2 Using Python as a Calculator**

Python can handle a variety of arithmetic operations just like a calculator. Try out each of the following in the interpreter or a script:

```python
# Basic operations
print(5 + 3)       # Addition: outputs 8
print(5 - 3)       # Subtraction: outputs 2
print(5 * 3)       # Multiplication: outputs 15
print(5 / 3)       # Division (float result): outputs 1.6667
print(5 // 3)      # Floor division (integer result): outputs 1
print(5 % 3)       # Modulus (remainder): outputs 2
print(5 ** 3)      # Exponentiation (power): outputs 125
```

Each operation will display an output. This can be a great way to start experimenting with basic commands in Python.

#### **2.3 Comments**

Comments are essential for documenting code. In Python:
- **Single-line comment**: Use `#` to mark a comment:
  ```python
  # This is a single-line comment
  print("Comments are ignored by the interpreter")
  ```
- **Multi-line comment**: Use triple quotes (`""" ... """`) to create a multi-line comment:
  ```python
  """
  This is a multi-line comment.
  It can span multiple lines.
  """
  ```

---

### **3. Key Functions for Beginners**

#### **3.1 The `print()` Function**

- **Basics of `print()`**:
  - The `print()` function is used to output data to the console. This function takes various types of data as input.
  ```python
  print("Welcome to Python")           # String
  print(123)                            # Integer
  print(3.14)                           # Float
  ```

- **Printing Multiple Items**:
  - You can separate items in `print()` with commas to print them on the same line:
    ```python
    print("Python version:", 3.10)
    ```

- **Using `sep` and `end` in `print()`**:
  - `sep`: Change the separator between multiple items.
  - `end`: Change what’s printed at the end of the output.
    ```python
    print("Hello", "World", sep="-")   # Output: Hello-World
    print("Hello", end="!")            # Output: Hello!
    ```

---

### **4. Hands-On Practice Exercises**

After going through these concepts, work through these exercises. Aim to solve each one to reinforce today’s learning.

1. **Exercise: Print Statements**
   - Write a script that prints:
     - A greeting message (e.g., "Welcome to Python").
     - Your favorite quote.
     - A fun fact about yourself.

2. **Exercise: Basic Math**
   - Calculate and print the result of the following expressions:
     - \( 10 + 15 \)
     - \( 45 - 12 \)
     - \( 8 \times 3 \)
     - \( 10 \div 2 \)
     - \( 7^2 \) (7 to the power of 2)
     - The remainder of dividing 17 by 3.
   - Write these in a Python script, and display each result on a new line.

3. **Exercise: Comments**
   - Write a script that contains at least five lines of code and comment each line to explain what it does.

4. **Exercise: Print Formatting**
   - Write a single line of code using `print()` that displays:
     ```plaintext
     Name: <Your Name>, Age: <Your Age>, Hobby: <Your Hobby>
     ```
   - Replace `<Your Name>`, `<Your Age>`, and `<Your Hobby>` with your details.

5. **Exercise: Explore `print()`**
   - Use `print()` to output:
     - The numbers 1 to 5 on the same line, separated by commas.
     - A message that ends with a custom punctuation mark (e.g., `"Hello there!"`).
   - Use the `sep` and `end` parameters to modify these print statements as needed.

---

### **5. Wrap-Up: Review and Reflect**

By the end of today, you should be comfortable with the basics of Python installation, using the interpreter, writing simple scripts, and utilizing the `print()` function effectively.

#### **Additional Tips**
- Keep experimenting with `print()` to understand its versatility.
- Practice running code in both the Python interpreter and saved scripts to understand how each approach works.

#### **Reflection Questions**
1. What are the benefits of using an interpreter versus a script?
2. How can you make your code more readable using comments?


### Hackerrank Problems
1. **[Hello World!](https://www.hackerrank.com/challenges/py-hello-world/problem)**


<p align="center">
  <a href="./Day02.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a>
</p>
