<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day07.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day09.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a></p>

## **Day 8: Tuples in Python**

### **Objective**
By the end of Day 8, You will understand tuples thoroughly, including how to create them, access their elements, and use built-in functions for tuple operations. She will also learn about when to choose tuples over lists and how to work with nested tuples and tuple unpacking.


### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=25)**
2.  **[Video 1](https://www.youtube.com/watch?v=ceiuLR2ysas&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=26)**
---

### **1. Theory**

#### **1.1 What is a Tuple?**

- A **tuple** in Python is an ordered, immutable collection of items. Unlike lists, tuples cannot be modified after creation.
- Tuples are defined using parentheses `()` and can store items of any data type.
  
- **Examples**:
  ```python
  coordinates = (10, 20)
  personal_info = ("Swati", 25, "Bhopal")
  ```

#### **1.2 Key Properties of Tuples**

- **Order is maintained**: Like lists, tuples maintain the order of elements.
- **Immutable**: Tuples cannot be changed after creation, meaning elements cannot be added, removed, or modified.
- **Allows duplicates**: Tuples can contain duplicate values.
- **Supports indexing and slicing**: We can access elements using indexes and slice tuples just like lists.

#### **1.3 Why Use Tuples?**

- **Data Integrity**: Tuples are useful for storing fixed collections of data where immutability is needed.
- **Efficiency**: Tuples are faster and use less memory compared to lists, so they are ideal for read-only data.
  
- **Examples of Usage**:
  - Storing geographical coordinates: `(latitude, longitude)`
  - Representing a fixed record, such as a date: `(year, month, day)`

---

### **2. Basic Operations with Tuples**

#### **2.1 Creating Tuples**

1. **Basic Tuple Creation**:
   ```python
   colors = ("red", "green", "blue")
   ```

2. **Single-Element Tuple**:
   - To create a tuple with one element, include a trailing comma.
   ```python
   single_element = (42,)
   print(type(single_element))  # Output: <class 'tuple'>
   ```

3. **Creating a Tuple without Parentheses**:
   - You can create a tuple without parentheses by separating values with commas.
   ```python
   dimensions = 800, 600
   print(dimensions)           # Output: (800, 600)
   ```

#### **2.2 Accessing Tuple Elements**

1. **Indexing**:
   - Access items using zero-based indexing.
   ```python
   colors = ("red", "green", "blue")
   print(colors[0])            # Output: red
   print(colors[2])            # Output: blue
   ```

2. **Negative Indexing**:
   - Use negative indices to access items from the end.
   ```python
   print(colors[-1])           # Output: blue
   ```

#### **2.3 Tuple Slicing**

- Slicing works the same as it does with lists.
  ```python
  numbers = (1, 2, 3, 4, 5)
  print(numbers[1:4])          # Output: (2, 3, 4)
  print(numbers[:3])           # Output: (1, 2, 3)
  print(numbers[::2])          # Output: (1, 3, 5)
  ```

#### **2.4 Nested Tuples**

- Tuples can contain other tuples as elements, creating a nested structure.
  ```python
  nested_tuple = (("apple", "banana"), (1, 2, 3))
  print(nested_tuple[0])       # Output: ('apple', 'banana')
  print(nested_tuple[1][1])    # Output: 2
  ```

---

### **3. Tuple Methods**

While tuples have limited methods compared to lists, they offer a few useful ones:

1. **`.count(item)`**: Counts occurrences of an item in a tuple.
   ```python
   numbers = (1, 2, 2, 3, 4, 2)
   print(numbers.count(2))     # Output: 3
   ```

2. **`.index(item)`**: Returns the index of the first occurrence of an item.
   ```python
   colors = ("red", "green", "blue", "green")
   print(colors.index("green")) # Output: 1
   ```

---

### **4. Tuple Operations**

#### **4.1 Concatenation and Repetition**

1. **Concatenation**:
   - Use `+` to combine two tuples.
   ```python
   tuple1 = (1, 2)
   tuple2 = (3, 4)
   combined = tuple1 + tuple2
   print(combined)             # Output: (1, 2, 3, 4)
   ```

2. **Repetition**:
   - Use `*` to repeat a tuple.
   ```python
   repeated = tuple1 * 3
   print(repeated)             # Output: (1, 2, 1, 2, 1, 2)
   ```

#### **4.2 Membership Check**

- Use `in` and `not in` to check for the presence of an item.
  ```python
  colors = ("red", "green", "blue")
  print("green" in colors)     # Output: True
  print("yellow" not in colors) # Output: True
  ```

#### **4.3 Tuple Unpacking**

- **Unpacking** allows assigning tuple elements to variables directly.
  ```python
  person = ("Swati", 25, "Engineer")
  name, age, profession = person
  print(name)                  # Output: Swati
  print(age)                   # Output: 25
  print(profession)            # Output: Engineer
  ```

- **Unpacking with `*` Operator**:
  - Use `*` to capture multiple elements in a list during unpacking.
  ```python
  numbers = (1, 2, 3, 4, 5)
  first, *middle, last = numbers
  print(first)                 # Output: 1
  print(middle)                # Output: [2, 3, 4]
  print(last)                  # Output: 5
  ```

---

### **5. Built-in Functions with Tuples**

Several built-in functions can be used with tuples:

1. **`len(tuple)`**: Returns the number of elements.
   ```python
   numbers = (1, 2, 3)
   print(len(numbers))         # Output: 3
   ```

2. **`min(tuple)` and `max(tuple)`**: Return the minimum and maximum values.
   ```python
   numbers = (5, 1, 9, 3)
   print(min(numbers))         # Output: 1
   print(max(numbers))         # Output: 9
   ```

3. **`sum(tuple)`**: Returns the sum of all elements.
   ```python
   print(sum(numbers))         # Output: 18
   ```

4. **`sorted(tuple)`**: Returns a sorted list of the tuple elements.
   ```python
   sorted_numbers = sorted(numbers)
   print(sorted_numbers)       # Output: [1, 3, 5, 9]
   ```

---

### **6. Practical Examples and Exercises**

#### **6.1 Storing and Accessing Data with Tuples**

1. **Geographical Coordinates**:
   - Store and print coordinates for a location.
   ```python
   location = (28.6139, 77.2090)  # Coordinates for New Delhi
   print("Latitude:", location[0])
   print("Longitude:", location[1])
   ```

2. **Unpacking Personal Information**:
   - Use tuple unpacking to store and print name, age, and profession.
   ```python
   person = ("Swati", 25, "Engineer")
   name, age, profession = person
   print(f"{name} is a {age}-year-old {profession}.")
   ```

#### **6.2 Tuple Operations**

1. **Combine Two Tuples**:
   - Concatenate and print two tuples.
   ```python
   colors1 = ("red", "green")
   colors2 = ("blue", "yellow")
   combined_colors = colors1 + colors2
   print(combined_colors)
   ```

2. **Repetition Example**:
   - Repeat a tuple three times.
   ```python
   basic_colors = ("red", "green", "blue")
   repeated_colors = basic_colors * 3
   print(repeated_colors)
   ```

#### **6.3 Using Built-in Functions**

1. **Find Maximum and Minimum**:
   - Use `max()` and `min()` to find the largest and smallest values in a tuple.
   ```python
   values = (10, 3, 15, 6, 9)
   print("Max:", max(values))
   print("Min:", min(values))
   ```

2. **Sorting a Tuple**:
   - Sort a tuple and return it as a list.
   ```python
   values = (5, 1, 3, 8, 

2)
   sorted_values = sorted(values)
   print(sorted_values)
   ```

---

### **7. Challenge Problems**

1. **Find Common Elements Between Two Tuples**:
   - Write a program to find common elements between two tuples.
   ```python
   tuple1 = (1, 2, 3, 4)
   tuple2 = (3, 4, 5, 6)
   common_elements = tuple(set(tuple1) & set(tuple2))
   print("Common elements:", common_elements)  # Output: (3, 4)
   ```

2. **Count Unique Elements**:
   - Write a program to count the unique elements in a tuple.
   ```python
   elements = (1, 2, 2, 3, 4, 4, 4, 5)
   unique_elements = len(set(elements))
   print("Number of unique elements:", unique_elements)  # Output: 5
   ```

3. **Convert a Tuple of Strings to Uppercase**:
   - Convert each string in a tuple to uppercase.
   ```python
   fruits = ("apple", "banana", "cherry")
   upper_fruits = tuple(fruit.upper() for fruit in fruits)
   print(upper_fruits)  # Output: ('APPLE', 'BANANA', 'CHERRY')
   ```

---

### **8. Wrap-Up: Review and Reflection**

By the end of today, You should be comfortable working with tuples, understand their immutability, and know how to use tuple methods and functions effectively.

#### **Reflection Questions**
1. Why might you choose a tuple over a list?
2. How do you create a tuple with only one element?
3. Can you modify a tuple after creation? Why or why not?

#### **Recap Quiz**
1. Write a tuple containing your favorite three colors.
2. How do you find the index of an item in a tuple?
3. Use tuple unpacking to assign `(1, 2, 3)` to three variables.

### Hackerrank Problems
1. [Tuples](https://www.hackerrank.com/challenges/python-tuples/problem?isFullScreen=true)
----------------------

<p align="center"> <a href="./Day07.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day09.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

---------------
