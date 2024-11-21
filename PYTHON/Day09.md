<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day08.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day10.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>


## **Day 9: Sets in Python**

### **Objective**
By the end of Day 9, You will understand how to use sets effectively, including creating sets, performing common operations, and using set methods. We’ll cover set theory concepts like union, intersection, difference, and symmetric difference, which are useful in many real-world applications.

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=l3kCO8cVA6o&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=31&ab_channel=CodeWithHarry)**
2. **[Video 2](https://www.youtube.com/watch?v=HOrutCnp2zo&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=32&ab_channel=CodeWithHarry)**
---

### **1. Theory**

#### **1.1 What is a Set?**

- A **set** in Python is an unordered, mutable collection of unique items. Sets are defined using curly braces `{}` or the `set()` function.
- **Important Properties of Sets**:
  - **Unordered**: Items are not stored in a specific order, so indexing and slicing aren’t possible.
  - **Mutable**: Sets can be modified by adding or removing items.
  - **Unique Elements**: Duplicate elements are automatically removed.

- **Examples**:
  ```python
  unique_numbers = {1, 2, 3, 4}
  fruits = {"apple", "banana", "cherry"}
  ```

#### **1.2 Creating Sets**

1. **Basic Set Creation**:
   ```python
   colors = {"red", "green", "blue"}
   ```

2. **Creating an Empty Set**:
   - Use `set()` to create an empty set, as `{}` creates an empty dictionary by default.
   ```python
   empty_set = set()
   ```

3. **Using `set()` with Other Iterables**:
   - Convert a list, tuple, or string to a set using `set()`.
   ```python
   numbers = set([1, 2, 2, 3, 4])  # Removes duplicates
   print(numbers)  # Output: {1, 2, 3, 4}
   ```

---

### **2. Basic Set Operations**

1. **Adding Elements**:
   - Use `.add(item)` to add an individual item.
   ```python
   colors = {"red", "green"}
   colors.add("blue")
   print(colors)  # Output: {'red', 'green', 'blue'}
   ```

2. **Updating with Multiple Items**:
   - Use `.update(iterable)` to add multiple items from an iterable (e.g., list, tuple).
   ```python
   colors.update(["yellow", "orange"])
   print(colors)  # Output: {'red', 'green', 'blue', 'yellow', 'orange'}
   ```

3. **Removing Elements**:
   - **`.remove(item)`**: Removes an item; raises an error if the item doesn’t exist.
   ```python
   colors.remove("red")
   ```
   - **`.discard(item)`**: Removes an item without an error if the item doesn’t exist.
   ```python
   colors.discard("purple")
   ```
   - **`.pop()`**: Removes and returns an arbitrary item (useful for emptying sets item by item).
   ```python
   item = colors.pop()
   print("Removed:", item)
   ```

4. **Clearing the Set**:
   - **`.clear()`**: Removes all items, making the set empty.
   ```python
   colors.clear()
   print(colors)  # Output: set()
   ```

---

### **3. Set Operations in Python**

Sets support several operations that are useful for working with collections:

1. **Union (`|` or `.union()`)**:
   - Combines all items from both sets, removing duplicates.
   ```python
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}
   union_set = set1 | set2
   print(union_set)  # Output: {1, 2, 3, 4, 5}
   ```

2. **Intersection (`&` or `.intersection()`)**:
   - Returns only items common to both sets.
   ```python
   intersection_set = set1 & set2
   print(intersection_set)  # Output: {3}
   ```

3. **Difference (`-` or `.difference()`)**:
   - Returns items that are in the first set but not in the second.
   ```python
   difference_set = set1 - set2
   print(difference_set)  # Output: {1, 2}
   ```

4. **Symmetric Difference (`^` or `.symmetric_difference()`)**:
   - Returns items in either set but not in both (excludes items common to both sets).
   ```python
   symmetric_difference = set1 ^ set2
   print(symmetric_difference)  # Output: {1, 2, 4, 5}
   ```

---

### **4. Set Methods and Built-in Functions**

#### **4.1 Membership Check**

- Use `in` and `not in` to check if an item exists in a set.
  ```python
  numbers = {1, 2, 3}
  print(1 in numbers)       # Output: True
  print(4 not in numbers)   # Output: True
  ```

#### **4.2 Other Useful Set Methods**

1. **`.isdisjoint(other_set)`**: Returns `True` if sets have no items in common.
   ```python
   set1 = {1, 2, 3}
   set2 = {4, 5}
   print(set1.isdisjoint(set2))  # Output: True
   ```

2. **`.issubset(other_set)`**: Checks if all elements of the set are in `other_set`.
   ```python
   set1 = {1, 2}
   set2 = {1, 2, 3}
   print(set1.issubset(set2))  # Output: True
   ```

3. **`.issuperset(other_set)`**: Checks if the set contains all elements of `other_set`.
   ```python
   print(set2.issuperset(set1))  # Output: True
   ```

#### **4.3 Built-in Functions for Sets**

1. **`len(set)`**: Returns the number of items in the set.
   ```python
   print(len(numbers))  # Output: 3
   ```

2. **`min(set)` and `max(set)`**: Return the minimum and maximum values in the set.
   ```python
   numbers = {5, 3, 8, 1}
   print(min(numbers))  # Output: 1
   print(max(numbers))  # Output: 8
   ```

3. **`sum(set)`**: Returns the sum of all items in the set.
   ```python
   print(sum(numbers))  # Output: 17
   ```

---

### **5. Practical Examples and Exercises**

#### **5.1 Removing Duplicates from a List**

- Convert a list with duplicate items to a set to remove duplicates.
  ```python
  items = ["apple", "banana", "apple", "cherry", "banana"]
  unique_items = set(items)
  print(unique_items)  # Output: {'apple', 'banana', 'cherry'}
  ```

#### **5.2 Finding Common Friends**

- Use set intersection to find common friends between two people.
  ```python
  swati_friends = {"Neha", "Rohan", "Amit"}
  rohan_friends = {"Amit", "Swati", "Raj"}
  common_friends = swati_friends & rohan_friends
  print("Common friends:", common_friends)  # Output: {'Amit'}
  ```

#### **5.3 Unique Words in a Sentence**

- Find unique words in a sentence.
  ```python
  sentence = "Learning Python is fun and Python is powerful"
  words = set(sentence.lower().split())
  print("Unique words:", words)
  ```

#### **5.4 Checking for Subset**

- Check if all essential supplies are available in the inventory.
  ```python
  inventory = {"notebook", "pen", "eraser", "marker", "ruler"}
  required_supplies = {"notebook", "pen"}
  print(required_supplies.issubset(inventory))  # Output: True
  ```

---

### **6. Challenge Problems**

1. **Find Unique Elements from Two Lists**
   - Write a program that finds unique elements from two lists using sets.
   ```python
   list1 = [1, 2, 3, 4]
   list2 = [3, 4, 5, 6]
   unique_elements = set(list1) ^ set(list2)
   print("Unique elements:", unique_elements)  # Output: {1, 2, 5, 6}
   ```

2. **Count Common Letters in Two Strings**
   - Find the common letters between two strings.
   ```python
   str1 = "python"
   str2 = "javascript"
   common_letters = set(str1) & set(str2)
   print("Common letters:", common_letters)  # Output: {'a', 't'}
   ```

3. **Identify Students Enrolled in Only One Class**
   - Given two sets of students in different classes, find students who are enrolled in only one of the classes.
   ```python
   class_A = {"Swati", "Amit", "Neha"}
   class_B = {"Rohan", "Neha", "Raj"}
   unique_students = class_A ^ class_B
   print("Students in only one class:", unique_students)  # Output: {'Swati', 'Amit', 'Rohan', 'Raj'}
   ```

---

### **7. Wrap-Up: Review and Reflection**

By the end of today, You should feel comfortable working with sets, performing set operations, and understanding the importance of unique collections.

#### **Reflection Questions**
1. When would you use a set instead of a list?
2. How does set intersection differ from union?
3. What is the result of using the `&` operator on two sets?

#### **Recap Quiz**
1. How do you add multiple elements to a set?
2. What’s the difference between `.remove()` and `.discard()`?
3. Write code to check if one set is a subset of another.

### Hackerrank Problems
1. [All 13 Questions](https://www.hackerrank.com/domains/python?filters%5Bsubdomains%5D%5B%5D=py-sets)
----------------------

<p align="center"> <a href="./Day08.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day10.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a></p>

---------------
