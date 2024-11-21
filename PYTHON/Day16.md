<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day15.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day17.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>



## **Day 16: File I/O in Python**

### **Objective**
By the end of Day 16, You will understand how to work with files in Python, including opening, reading, writing, appending, and managing file pointers using `seek` and `tell`. This session will also include handling file modes, file methods, and best practices.


### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=eDBPlcWYses&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=49&ab_channel=CodeWithHarry)**
2. **[Video 2](https://www.youtube.com/watch?v=l1FsnQxET9U&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=50&ab_channel=CodeWithHarry)**
3. **[Vid 3](https://www.youtube.com/watch?v=PByYX-2l5Us&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=51&ab_channel=CodeWithHarry)**
---

### **1. Theory: File Handling Basics**

#### **1.1 What is File I/O?**
- File I/O refers to reading from and writing to files stored on a disk. Python provides built-in methods to handle file operations efficiently.

#### **1.2 File Open Modes**
- Files in Python can be opened using the built-in `open()` function. The file mode determines what operations can be performed.
  
- **Modes**:
  | Mode | Description                                |
  |------|--------------------------------------------|
  | `'r'` | Read-only mode. File must exist.          |
  | `'w'` | Write mode. Overwrites the file if it exists; creates a new file otherwise. |
  | `'a'` | Append mode. Adds content to the end of the file. |
  | `'x'` | Exclusive creation. Fails if the file exists. |
  | `'b'` | Binary mode. Used for non-text files.     |
  | `'t'` | Text mode (default).                     |
  | `'+'` | Read and write mode.                     |

- **Examples**:
  ```python
  # Open a file in read mode
  file = open("example.txt", "r")

  # Open a file in write mode
  file = open("example.txt", "w")
  ```

#### **1.3 The `with` Statement**
- Using `with` ensures the file is properly closed after operations, even if an exception occurs.
- **Example**:
  ```python
  with open("example.txt", "r") as file:
      content = file.read()
      print(content)  # File automatically closes after this block
  ```

---

### **2. Reading Files**

#### **2.1 The `read()` Method**
- Reads the entire content of the file as a single string.
- **Syntax**:
  ```python
  file.read(size)
  ```
  - `size` (optional): Number of bytes to read. Reads all content if not specified.
  
- **Example**:
  ```python
  with open("example.txt", "r") as file:
      content = file.read()
      print(content)
  ```
  **Output** *(if `example.txt` contains "Hello, World!")*:
  ```
  Hello, World!
  ```

#### **2.2 The `readline()` Method**
- Reads one line from the file at a time.
- **Example**:
  ```python
  with open("example.txt", "r") as file:
      line = file.readline()
      print(line)
  ```
  **Output** *(if the first line is "Python is fun.")*:
  ```
  Python is fun.
  ```

#### **2.3 The `readlines()` Method**
- Reads all lines in the file and returns them as a list of strings.
- **Example**:
  ```python
  with open("example.txt", "r") as file:
      lines = file.readlines()
      print(lines)
  ```
  **Output**:
  ```
  ['Python is fun.\n', 'File handling is useful.\n']
  ```

---

### **3. Writing to Files**

#### **3.1 The `write()` Method**
- Writes a single string to the file.
- **Example**:
  ```python
  with open("output.txt", "w") as file:
      file.write("Hello, Swati!")
  ```
  **Creates a file** `output.txt` with:
  ```
  Hello, Swati!
  ```

#### **3.2 The `writelines()` Method**
- Writes a list of strings to the file.
- **Example**:
  ```python
  lines = ["Python is great.\n", "File I/O is powerful.\n"]
  with open("output.txt", "w") as file:
      file.writelines(lines)
  ```
  **Creates a file** `output.txt` with:
  ```
  Python is great.
  File I/O is powerful.
  ```

---

### **4. File Pointers and the `seek()` and `tell()` Methods**

#### **4.1 The `tell()` Method**
- Returns the current position of the file pointer in bytes.
- **Example**:
  ```python
  with open("example.txt", "r") as file:
      print(file.tell())  # Output: 0 (start of file)
      file.read(5)
      print(file.tell())  # Output: 5 (after reading 5 bytes)
  ```

#### **4.2 The `seek()` Method**
- Moves the file pointer to a specific position.
- **Syntax**:
  ```python
  file.seek(offset, whence)
  ```
  - `offset`: Number of bytes to move.
  - `whence`: Starting point (`0` for start, `1` for current position, `2` for end).

- **Example**:
  ```python
  with open("example.txt", "r") as file:
      file.seek(7)  # Move to the 7th byte
      print(file.read(5))  # Reads 5 bytes from the 7th position
  ```
  **Output** *(if `example.txt` contains "Hello, World!")*:
  ```
  World
  ```

#### **4.3 Combining `seek()` and `tell()`**
- **Example**:
  ```python
  with open("example.txt", "r") as file:
      print("Initial Position:", file.tell())
      file.seek(5)
      print("After Seek:", file.tell())
      content = file.read()
      print("Final Content:", content)
  ```
  **Output** *(if `example.txt` contains "Hello, World!")*:
  ```
  Initial Position: 0
  After Seek: 5
  Final Content: , World!
  ```

---

### **5. Additional File Operations**

#### **5.1 Checking File Existence**
- Use the `os` module to check if a file exists.
- **Example**:
  ```python
  import os
  print(os.path.exists("example.txt"))  # Output: True or False
  ```

#### **5.2 Renaming and Deleting Files**
- Use the `os` module to rename or delete files.
- **Renaming**:
  ```python
  os.rename("old_name.txt", "new_name.txt")
  ```
- **Deleting**:
  ```python
  os.remove("example.txt")
  ```

#### **5.3 Reading and Writing Binary Files**
- Open files in binary mode (`'b'`).
- **Example**:
  ```python
  with open("image.jpg", "rb") as file:
      data = file.read()

  with open("copy.jpg", "wb") as copy:
      copy.write(data)
  ```

---

### **6. Practical Exercises**

#### **6.1 Reading a File and Counting Words**
- Write a program to read a file and count the number of words.
  ```python
  with open("example.txt", "r") as file:
      content = file.read()
      word_count = len(content.split())
      print(f"Word count: {word_count}")
  ```

#### **6.2 Reversing the Content of a File**
- Write a program to reverse the content of a file and save it in a new file.
  ```python
  with open("example.txt", "r") as file:
      content = file.read()

  with open("reversed.txt", "w") as file:
      file.write(content[::-1])
  ```

#### **6.3 Copying a File**
- Write a program to copy the content of one file to another.
  ```python
  with open("source.txt", "r") as source:
      content = source.read()

  with open("destination.txt", "w") as destination:
      destination.write(content)
  ```

#### **6.4 Using `seek` to Read a File Backward**
- Write a program to read a file backward using `seek()`.
  ```python
  with open("example.txt", "r") as file:
      file.seek(0, 2)  # Move to the end of the file
      position = file.tell()
      while position > 0:
          position -= 1
          file.seek(position)
          print(file.read(1), end="")
  ```

---

### **7. Wrap-Up: Review and Reflection**

By the end of today, you should feel confident working with files, understanding file modes, and utilizing advanced methods like `seek` and `tell` to manipulate file pointers.

#### **Reflection Questions**
1. Why is it important to use the `with` statement when working with files?
2. What is the difference between `read()` and `readlines()`?
3. How does the `seek()` method work in binary files?

#### **Recap Quiz**
1. Write a program to append text to an existing file.
2. How do you move the file pointer to the beginning of a file after reading it halfway?
3. What happens if you try to read a non-existent file in `'r'` mode?


----------------

<p align="center"> <a href="./Day15.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day17.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

---------------
