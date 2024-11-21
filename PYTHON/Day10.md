<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day09.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day11.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

## **Day 10: Dictionaries in Python**

### **Objective**
By the end of Day 10, you will understand how to use dictionaries, including creating, accessing, updating, and using various dictionary methods. She’ll also learn how to nest dictionaries and work with dictionary comprehension for concise data manipulation.

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=j2G68uQtOwM&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=33&ab_channel=CodeWithHarry)**
2. **[Video 2](https://www.youtube.com/watch?v=LmbFwaLjT9k&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=34&ab_channel=CodeWithHarry)**
---
---

### **1. Theory**

#### **1.1 What is a Dictionary?**

- A **dictionary** in Python is an unordered, mutable collection of items stored as **key-value pairs**. Each key in a dictionary is unique and acts as an identifier for its corresponding value.
- **Syntax**:
  ```python
  dictionary = {
      "key1": "value1",
      "key2": "value2"
  }
  ```
  
- **Examples**:
  ```python
  student_info = {
      "name": "Swati",
      "age": 25,
      "city": "Bhopal"
  }
  ```

#### **1.2 Key Properties of Dictionaries**

- **Unordered**: Dictionaries don’t maintain order until Python 3.7, where they preserve insertion order.
- **Mutable**: Dictionaries can be modified by adding, updating, or removing key-value pairs.
- **Unique Keys**: Each key in a dictionary must be unique, while values can be duplicated.
- **Keys must be immutable**: Common types used as keys include strings, numbers, and tuples (as they are immutable), while lists or other dictionaries cannot be keys.

---

### **2. Basic Dictionary Operations**

#### **2.1 Creating a Dictionary**

1. **Basic Dictionary**:
   ```python
   car = {
       "brand": "Toyota",
       "model": "Camry",
       "year": 2020
   }
   ```

2. **Using `dict()` Constructor**:
   ```python
   person = dict(name="Swati", age=25, city="Bhopal")
   ```

#### **2.2 Accessing Values**

- **Using Keys**:
  - Access values by using the key inside square brackets `[]`.
  ```python
  print(student_info["name"])  # Output: Swati
  ```
  - If the key doesn’t exist, Python raises a `KeyError`.

- **Using `.get()` Method**:
  - Returns the value for a key, but won’t raise an error if the key is missing (returns `None` or a specified default value).
  ```python
  print(student_info.get("age"))             # Output: 25
  print(student_info.get("gender", "N/A"))   # Output: N/A
  ```

#### **2.3 Adding and Updating Values**

1. **Adding New Key-Value Pairs**:
   - Assign a new key and value directly.
   ```python
   student_info["course"] = "Data Science"
   print(student_info)
   ```

2. **Updating Values**:
   - Use the same syntax to update an existing key.
   ```python
   student_info["age"] = 26
   ```

#### **2.4 Removing Key-Value Pairs**

1. **`.pop(key)`**:
   - Removes a key-value pair and returns the value. Raises an error if the key doesn’t exist.
   ```python
   age = student_info.pop("age")
   print(age)                  # Output: 25
   ```

2. **`.popitem()`**:
   - Removes and returns the last inserted key-value pair. Useful in Python 3.7+.
   ```python
   item = student_info.popitem()
   print(item)                 # Output: ('course', 'Data Science')
   ```

3. **`del dictionary[key]`**:
   - Deletes a specific key-value pair.
   ```python
   del student_info["city"]
   ```

4. **`.clear()`**:
   - Empties the dictionary.
   ```python
   student_info.clear()
   ```

---

### **3. Dictionary Methods and Built-in Functions**

#### **3.1 Accessing All Keys, Values, and Items**

1. **`.keys()`**:
   - Returns a view of all keys in the dictionary.
   ```python
   keys = student_info.keys()
   ```

2. **`.values()`**:
   - Returns a view of all values in the dictionary.
   ```python
   values = student_info.values()
   ```

3. **`.items()`**:
   - Returns a view of all key-value pairs as tuples.
   ```python
   items = student_info.items()
   ```

#### **3.2 Checking Key Existence**

- Use `in` and `not in` to check if a key exists in the dictionary.
  ```python
  if "name" in student_info:
      print("Name exists")
  ```

#### **3.3 Merging Dictionaries**

1. **`.update(other_dict)`**:
   - Updates a dictionary with key-value pairs from another dictionary. Existing keys will be updated, and new keys will be added.
   ```python
   additional_info = {"country": "India", "age": 26}
   student_info.update(additional_info)
   print(student_info)
   ```

#### **3.4 Dictionary Comprehension**

**Dictionary comprehension** offers a compact way to create dictionaries.

- **Syntax**:
  ```python
  {key_expression: value_expression for item in iterable if condition}
  ```

- **Examples**:

1. **Simple Dictionary Comprehension**:
   - Create a dictionary of squares for numbers from 1 to 5.
   ```python
   squares = {x: x**2 for x in range(1, 6)}
   ```

2. **Filtering Data**:
   - Create a dictionary with only even numbers from 1 to 10 and their squares.
   ```python
   evens = {x: x**2 for x in range(1, 11) if x % 2 == 0}
   ```

---

### **4. Nested Dictionaries**

Dictionaries can contain other dictionaries, creating a nested structure.

- **Example**:
  ```python
  company = {
      "department1": {
          "manager": "Swati",
          "employees": 10
      },
      "department2": {
          "manager": "Amit",
          "employees": 15
      }
  }

  print(company["department1"]["manager"])  # Output: Swati
  ```

---

### **5. Practical Examples and Exercises**

#### **5.1 Creating a Contact Book**

- Use a dictionary to store contacts with names as keys and phone numbers as values.
  ```python
  contacts = {
      "Swati": "123-456-7890",
      "Amit": "234-567-8901"
  }
  ```

#### **5.2 Using Dictionary Comprehension**

1. **Generate a Dictionary of Cubes**:
   - Create a dictionary of cubes for numbers from 1 to 5.
   ```python
   cubes = {x: x**3 for x in range(1, 6)}
   print(cubes)
   ```

2. **Inverting a Dictionary**:
   - Swap keys and values of a dictionary.
   ```python
   original = {"a": 1, "b": 2, "c": 3}
   inverted = {value: key for key, value in original.items()}
   print(inverted)  # Output: {1: 'a', 2: 'b', 3: 'c'}
   ```

#### **5.3 Handling Inventory with Nested Dictionaries**

- Create a nested dictionary to manage inventory items and their details.
  ```python
  inventory = {
      "apples": {"quantity": 50, "price": 0.5},
      "bananas": {"quantity": 100, "price": 0.3}
  }

  print(inventory["apples"]["quantity"])  # Output: 50
  ```

---

### **6. Challenge Problems**

1. **Count Character Frequency**:
   - Write a program to count the frequency of each character in a string.
   ```python
   text = "hello world"
   char_count = {}
   for char in text:
       char_count[char] = char_count.get(char, 0) + 1
   print(char_count)
   ```

2. **Group Students by Grade**:
   - Given a list of students and their grades, group students by their grades using a dictionary.
   ```python
   students = [("Swati", "A"), ("Amit", "B"), ("Neha", "A"), ("Raj", "B")]
   grades = {}
   for name, grade in students:
       grades.setdefault(grade, []).append(name)
   print(grades)  # Output: {'A': ['Swati', 'Neha'], 'B': ['Amit', 'Raj']}
   ```

3. **Merge Two Dictionaries and Sum Values for Common Keys**:
   - Given two dictionaries with integer values, merge them and sum the values of common keys.
   ```python
   dict1 = {"a": 2, "b": 3, "c": 5}
   dict2 = {"b": 4, "c": 1, "d": 7}
   merged = {k: dict1.get(k, 0) + dict2.get(k, 0) for k in dict1.keys() | dict2.keys()}
   print(merged)  # Output: {'a': 2, 'b': 7, 'c': 6, 'd': 7}
   ```

---

### **7. Wrap-Up: Review and Reflection**

By the end of today, you should feel comfortable using dictionaries, working with nested dictionaries, and applying dictionary comprehension.

#### **Reflection Questions**
1. How is accessing values in a dictionary different from a list?
2. What are some benefits of using dictionaries over lists?
3. How can dictionary comprehension simplify your code?

#### **Recap Quiz**
1. Write code to add a new key-value pair to a dictionary.
2. How do you remove a key-value pair from a dictionary?
3. Create a dictionary comprehension that maps numbers to their squares for values 1 through 5.

---
### Hackerrank Problems
1. [no problem found](#)
----------------------
<p align="center"> <a href="./Day09.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day11.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>
