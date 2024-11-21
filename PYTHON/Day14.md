<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day13.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day15.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>


## Day 14: **Understanding Python Imports, `__name__ == "__main__"` and the OS Module**

This comprehensive guide will walk you through:
1. **The `import` statement in Python** (how to import and use modules, packages, and custom modules).
2. **The significance of `if __name__ == "__main__"`** (its role in Python scripts).
3. **The OS module** (working with the operating system through Python).

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=Pr7UOr35NcI&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=44&ab_channel=CodeWithHarry)**
2. **[Video 2](https://www.youtube.com/watch?v=y_CX2Rvitk8&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=45&ab_channel=CodeWithHarry)**
3. **[Video 3](https://www.youtube.com/watch?v=dkVYSsL90Oo&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=46&ab_channel=CodeWithHarry)**
---
---

## **1. The `import` Statement in Python**

### **What is the `import` statement?**
The `import` statement is used to include external modules and packages into your Python program. These modules can be either built-in Python modules or external libraries that you install via package managers like `pip`.

Importing allows you to:
- Reuse code and avoid redundancy.
- Access functionalities such as mathematical operations, system handling, file handling, etc., without writing the code from scratch.

---

### **Types of Imports:**

1. **Importing Entire Modules:**
   When you import an entire module, you can access its functions, classes, and variables by prefixing the module name.

   ```python
   import math
   print(math.sqrt(16))  # Access sqrt function from the math module
   ```

2. **Importing Specific Functions/Variables from a Module:**
   Instead of importing the entire module, you can import specific functions or variables, making your code more concise.

   ```python
   from math import sqrt
   print(sqrt(16))  # Direct access to sqrt without module name
   ```

3. **Importing with Aliases:**
   You can import a module and give it an alias to make it easier to reference.

   ```python
   import numpy as np
   arr = np.array([1, 2, 3])  # Using alias np for numpy
   ```

4. **Importing All Functions and Variables:**
   While not recommended due to potential naming conflicts, you can import everything from a module using the `*` syntax.

   ```python
   from math import *
   print(sqrt(16))  # Direct access to sqrt, pi, etc.
   ```

---

### **Working with Built-in Modules**

Python has a wide range of built-in modules like `math`, `os`, `sys`, `datetime`, etc., that provide various functionalities.

```python
import sys
print(sys.version)  # Prints the current Python version
```

### **Creating Your Own Modules**

A Python module is simply a file containing Python code (e.g., `module_name.py`). You can import your own Python files in the same way as external modules.

- Create a file `my_module.py` with functions:
  ```python
  # my_module.py
  def greet(name):
      return f"Hello, {name}!"
  ```

- Then, in another file, import and use the module:
  ```python
  import my_module
  print(my_module.greet("Alice"))
  ```

---

### **The `__init__.py` File and Packages**

A **package** is a collection of modules in a directory. For Python to recognize a directory as a package, it needs an `__init__.py` file inside that directory. This file can be empty or contain initialization code for the package.

For example:
```
mypackage/
    __init__.py
    module1.py
    module2.py
```

You can import the package as follows:
```python
from mypackage import module1
```

---

## **2. The `if __name__ == "__main__"` Construct in Python**

### **What is `if __name__ == "__main__"`?**

In Python, `__name__` is a special built-in variable. It is set to the name of the module when the module is imported. However, if the module is run as a standalone script, `__name__` is set to `"__main__"`.

The `if __name__ == "__main__"` block allows you to execute certain code only when the module is run directly and not when it is imported.

### **Why Use `if __name__ == "__main__"`?**

1. **Script Execution**: It ensures that certain parts of the code are executed only when the file is run directly, not when imported as a module.
2. **Modularity**: You can separate the code for module functionality and script execution. This is useful when your code can both be reused as a module or executed as a standalone script.

#### **Example:**
```python
# mymodule.py
def greet(name):
    print(f"Hello, {name}!")

if __name__ == "__main__":
    greet("Alice")  # This will execute only if mymodule.py is run directly
```

If you run `mymodule.py` directly, it will print `"Hello, Alice!"`. However, if you import `mymodule.py` into another script, the `greet()` function won't be executed unless explicitly called.

```python
# script.py
import mymodule  # The greet function is available but won't run automatically
```

### **How it Works:**
1. **When running a script directly**, Python sets `__name__` to `"__main__"`. Any code under `if __name__ == "__main__":` will execute.
2. **When importing a module**, `__name__` is set to the module's name (e.g., `mymodule`), and the block under `if __name__ == "__main__":` does not execute.

---

## **3. The OS Module in Python**

The `os` module in Python provides a way to interact with the operating system. It allows you to perform tasks like navigating the file system, handling files and directories, managing environment variables, and more.

### **Common Functions in the OS Module**

1. **File and Directory Operations:**
   - **`os.getcwd()`**: Get the current working directory.
   - **`os.chdir(path)`**: Change the current working directory.
   - **`os.listdir(path)`**: List all files and directories in a specified path.
   - **`os.mkdir(path)`**: Create a directory.
   - **`os.remove(path)`**: Remove a file.
   - **`os.rename(old, new)`**: Rename a file or directory.

   ```python
   import os
   print(os.getcwd())  # Current working directory
   os.mkdir("new_folder")  # Create a new folder
   os.rename("new_folder", "renamed_folder")  # Rename folder
   ```

2. **Path Manipulation:**
   The `os.path` submodule provides functions to manipulate file and directory paths.

   - **`os.path.join(path1, path2)`**: Join two or more paths.
   - **`os.path.exists(path)`**: Check if a file or directory exists.
   - **`os.path.basename(path)`**: Get the base name (file or folder) from the path.
   - **`os.path.dirname(path)`**: Get the directory name from the path.

   ```python
   import os
   path = "/home/user/docs/file.txt"
   print(os.path.basename(path))  # Output: file.txt
   print(os.path.dirname(path))  # Output: /home/user/docs
   ```

3. **Environment Variables:**
   You can access environment variables (e.g., system settings or user-specific settings).

   - **`os.environ`**: A dictionary-like object containing environment variables.
   - **`os.getenv('VAR_NAME')`**: Get the value of an environment variable.
   - **`os.putenv('VAR_NAME', 'value')`**: Set the value of an environment variable.

   ```python
   import os
   print(os.environ['HOME'])  # Prints the home directory (on Unix-based systems)
   os.putenv("MY_VAR", "value")  # Set a new environment variable
   ```

4. **Process Management:**
   The `os` module can also be used for interacting with system processes:
   
   - **`os.system(command)`**: Execute a command in the system shell.
   - **`os.getpid()`**: Get the current process ID.

   ```python
   os.system("echo 'Hello World!'")  # Executes the shell command
   print(os.getpid())  # Prints the current process ID
   ```

5. **Working with Temporary Files:**
   The `os` module also provides functionality to handle temporary files.

   - **`os.tmpnam()`**: Generate a unique temporary file name.
   - **`os.tempnam()`**: Create a temporary file (deprecated, use `tempfile` module instead).

---

### **Summary of Concepts:**

- **Importing Modules**: Python allows importing built-in and custom modules using the `import` statement, which enhances code reuse and modularity.
- **`__name__ == "__main__"`**: This construct allows you to separate code meant for script execution from code meant for reuse as a module.
- **The OS Module**: The `os` module provides a powerful interface to interact with the underlying operating system, handle files, directories, environment variables, and processes.

---

### **Exercises to Master These Concepts:**

1. **Import Practice**: Create a Python file with some functions, then import and use those functions in another file.
2. **Use `if __name__ == "__main__"`**: Write a script that includes a function under the `if __name__ == "__main__"` block and test its behavior when run directly vs. imported.
3. **File Handling**:

 Use the `os` module to navigate directories, create files, and list files in a directory.
4. **Environment Variables**: Set and retrieve environment variables using `os.getenv()` and `os.putenv()`.

---

### **Conclusion**

By now, you should have a solid understanding of:
- How to import and use both built-in and custom Python modules.
- The significance of `if __name__ == "__main__"` for controlling script execution.
- How to use the `os` module for interacting with the operating system, file systems, and processes.

---
### Hackerrank Problems
1. [no problem found](#)
----------------------


<p align="center"> <a href="./Day13.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day15.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>
