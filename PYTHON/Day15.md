<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day14.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day16.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

### **Day 15: Understanding Virtual Environments and Local/Global Variables in Python**

In this guide, we'll explore:
1. **Virtual Environments in Python** – Why and how to create and use them.
2. **Local and Global Variables in Python** – Their scopes and usage.

## Videos

[Vid 1](https://www.youtube.com/watch?v=nt6LlFTWOkg&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=43&ab_channel=CodeWithHarry)
[Vid 2](https://www.youtube.com/watch?v=RaG6GgcDt54&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=48&ab_channel=CodeWithHarry)

---

## **1. Virtual Environments in Python**

### **What is a Virtual Environment?**

A virtual environment (virtualenv) is a self-contained directory that contains a Python installation and additional libraries, independent of the global Python installation on your system. It allows you to:
- Manage dependencies for specific projects.
- Prevent conflicts between different versions of libraries for different projects.
- Keep your global Python environment clean and free of unnecessary packages.

### **Why Use Virtual Environments?**
1. **Isolation**: Keeps dependencies for different projects isolated from each other.
2. **Versioning**: You can work with specific versions of libraries that a project requires.
3. **Avoid Conflicts**: Prevents version conflicts between different projects. For instance, one project may need `Django 2.x` while another requires `Django 3.x`.
4. **Portability**: You can easily share a project along with its virtual environment, ensuring that others work with the same dependencies.

---

### **How to Create and Manage a Virtual Environment**

1. **Install `virtualenv` (if not using `venv`):**
   If you're using Python 3.3+ you already have the `venv` module, but for earlier versions, you'll need `virtualenv`:

   ```bash
   pip install virtualenv
   ```

2. **Creating a Virtual Environment (Using `venv`)**:
   - **Windows**:
     ```bash
     python -m venv myenv
     ```
   - **Mac/Linux**:
     ```bash
     python3 -m venv myenv
     ```

   This command creates a directory named `myenv` (you can name it anything), and inside it, you’ll find a self-contained Python installation with its own `bin` and `lib` folders.

3. **Activating the Virtual Environment**:
   - **Windows**:
     ```bash
     myenv\Scripts\activate
     ```
   - **Mac/Linux**:
     ```bash
     source myenv/bin/activate
     ```

   Once activated, your terminal will show the name of the environment, indicating that you are working within that environment.

4. **Installing Packages in the Virtual Environment**:
   Once the virtual environment is activated, you can install any packages using `pip`, and they will be installed only for that specific environment.

   ```bash
   pip install numpy
   ```

5. **Deactivating the Virtual Environment**:
   When you're done working, you can deactivate the virtual environment to return to your global environment:

   ```bash
   deactivate
   ```

---

### **Working with Requirements Files**

To manage dependencies for a project, you can create a `requirements.txt` file that lists all the packages needed for the project.

1. **Generate `requirements.txt`**:
   You can generate this file by running:

   ```bash
   pip freeze > requirements.txt
   ```

2. **Install Packages from `requirements.txt`**:
   When setting up a new virtual environment for a project, you can install all required packages with:

   ```bash
   pip install -r requirements.txt
   ```

This ensures that all dependencies are installed with the correct versions.

---

### **Advantages of Virtual Environments**
- **Environment Isolation**: You can run different versions of the same package across multiple projects without interference.
- **Cleaner Global Environment**: Prevents unnecessary installations in your global Python environment.
- **Project Portability**: It’s easy to move or share a project along with its environment and dependencies.

---

## **2. Local and Global Variables in Python**

### **What Are Variables in Python?**

Variables in Python are used to store data that can be referenced and manipulated throughout the program. The scope (where the variable can be accessed) and lifetime (how long the variable exists) of a variable depends on where it is defined.

---

### **Global Variables**

#### **What is a Global Variable?**
A **global variable** is defined outside any function or class and can be accessed from any part of the program.

- **Scope**: Global variables can be accessed anywhere in the code.
- **Lifetime**: They exist as long as the program runs.

#### **How to Use Global Variables?**
1. **Defining Global Variables**:
   You define a global variable outside any functions:

   ```python
   global_var = 10  # Global variable

   def print_global():
       print(global_var)

   print_global()  # Outputs: 10
   ```

2. **Modifying Global Variables Inside Functions**:
   You can access a global variable from inside a function, but to modify it, you need to use the `global` keyword.

   ```python
   global_var = 10  # Global variable

   def modify_global():
       global global_var  # Declare it as global inside the function
       global_var = 20  # Modify the global variable

   modify_global()
   print(global_var)  # Outputs: 20
   ```

   If you don’t use the `global` keyword, Python treats the variable as a **local variable**, which means the global variable won’t be modified.

3. **Good Practices**:
   - Global variables should be used sparingly to avoid code that is hard to debug or maintain.
   - Avoid over-relying on global variables to store state; they can cause side effects that are hard to track.

---

### **Local Variables**

#### **What is a Local Variable?**
A **local variable** is defined inside a function and is only accessible within that function. Once the function call finishes, the variable is destroyed.

- **Scope**: Local to the function in which it is declared.
- **Lifetime**: Exists only during the function execution.

#### **How to Use Local Variables?**
1. **Defining Local Variables**:
   You define local variables inside a function, and they can only be accessed within that function.

   ```python
   def my_function():
       local_var = 5  # Local variable
       print(local_var)

   my_function()  # Outputs: 5
   # print(local_var)  # Raises NameError: name 'local_var' is not defined
   ```

2. **Accessing Local Variables**:
   Local variables cannot be accessed outside their function:

   ```python
   def my_function():
       local_var = 5

   my_function()
   # print(local_var)  # Raises NameError
   ```

---

### **Global vs Local Variables**

The same variable name can exist as both a local and a global variable, but Python will give precedence to the **local variable** within the function.

```python
x = 10  # Global variable

def my_function():
    x = 20  # Local variable
    print(x)  # Outputs: 20

my_function()
print(x)  # Outputs: 10 (Global variable is unaffected)
```

If you want to modify the global variable inside a function, use the `global` keyword.

---

### **The `global` Keyword**
You use the `global` keyword to modify a global variable inside a function:

```python
x = 10  # Global variable

def modify_global():
    global x  # Declare x as global
    x = 20  # Modify global variable

modify_global()
print(x)  # Outputs: 20
```

### **The `nonlocal` Keyword**
The `nonlocal` keyword is used to modify variables in the **enclosing scope** (not global). It’s often used with nested functions.

```python
def outer():
    x = 10  # Enclosing variable

    def inner():
        nonlocal x  # Modify variable in enclosing scope
        x = 20

    inner()
    print(x)  # Outputs: 20

outer()
```

Without the `nonlocal` keyword, the inner function would create a new local variable `x` and not modify the one in the outer scope.

---

### **Local and Global Variables: Best Practices**

- **Limit Global Variables**: Relying too much on global variables can make your code harder to understand and debug.
- **Encapsulate Variables Inside Functions**: Use local variables to limit scope and avoid side effects.
- **Use Functions for Reusability**: If you need global-like behavior, consider passing variables explicitly to functions rather than relying on the global scope.

---

## **Summary**

1. **Virtual Environments**: Virtual environments allow you to isolate project dependencies, ensuring that different projects can work with different package versions without conflicts.
   - You can create, activate, and deactivate virtual environments using `venv` or `virtualenv`.
   - Use `requirements.txt` to manage dependencies for your project.

2. **Global and Local Variables**:
   - **Global Variables** are accessible from anywhere in the code and last for the entire program's lifetime.
   - **Local Variables** are confined to the function or block in which they are declared.
   - Use the `global` keyword to modify global variables inside a function, and the `nonlocal` keyword to modify variables in enclosing scopes (but not global).

---
### Hackerrank Problems
1. [no problem found](#)
----------------------

<p align="center"> <a href="./Day14.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day16.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>
