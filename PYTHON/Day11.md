<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day02.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day04.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>


## **Day 11: Advance Python Functions**

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=kGnYc_h1geM&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=42&ab_channel=CodeWithHarry)**
2. **[Video 2](https://www.youtube.com/watch?v=OErhjT4f5Cs&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=53&ab_channel=CodeWithHarry)**
3. **[Video 3](https://www.youtube.com/watch?v=UfFWf-PXUqE&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=52&ab_channel=CodeWithHarry)**
4. **[Video 4](https://www.youtube.com/watch?v=bthQCK1QAmQ&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=16&ab_channel=CodeWithHarry)**

---

## **1. `enumerate()` in Python** 

### **Theory & Concept:**
The `enumerate()` function adds a counter to an iterable, such as a list, tuple, or string. This function returns an **enumerate object** (which is an iterator), consisting of pairs (index, value). 

The major advantage of using `enumerate()` is its ability to keep track of the index while iterating through an iterable, making your code more efficient and cleaner.

### **Basic Syntax:**
```python
enumerate(iterable, start=0)
```

- `iterable`: The iterable (list, tuple, etc.).
- `start`: The starting index for counting (default is `0`).

---

### **Basic Example:**

```python
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(index, fruit)
```
**Output:**
```
0 apple
1 banana
2 cherry
```

---

### **Advanced Use Cases:**

#### **1.1 Custom Starting Index**

```python
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits, start=1):
    print(index, fruit)
```

**Output:**
```
1 apple
2 banana
3 cherry
```

#### **1.2 Using `enumerate()` to Build Dictionaries**

```python
fruits = ["apple", "banana", "cherry"]
fruit_dict = {index: fruit for index, fruit in enumerate(fruits)}
print(fruit_dict)
```

**Output:**
```
{0: 'apple', 1: 'banana', 2: 'cherry'}
```

#### **1.3 Using `enumerate()` with `zip()` for Multiple Iterables**

```python
names = ["John", "Jane", "Doe"]
ages = [28, 22, 35]

for index, (name, age) in enumerate(zip(names, ages)):
    print(index, name, age)
```

**Output:**
```
0 John 28
1 Jane 22
2 Doe 35
```

---

### **Exercise 1:**

1. Create a list of numbers and use `enumerate()` to print each number with its square.
2. Create a dictionary using `enumerate()` where keys are the index and values are uppercase names from a list of strings.

---

## **2. `map()` in Python**

### **Theory & Concept:**
`map()` is a function that allows you to apply a given function to all items in an iterable (like a list, tuple, or string). It returns a **map object** that is an iterator, so you can convert it to a list or tuple.

The main purpose of `map()` is to simplify data transformations in an iterable without using explicit loops.

### **Basic Syntax:**
```python
map(function, iterable, ...)
```

- `function`: A function that is applied to each element of the iterable.
- `iterable`: One or more iterable objects (e.g., list, tuple).

---

### **Basic Example:**

```python
numbers = [1, 2, 3, 4]
result = map(lambda x: x * 2, numbers)
print(list(result))
```
**Output:**
```
[2, 4, 6, 8]
```

---

### **Advanced Use Cases:**

#### **2.1 Mapping with Multiple Iterables**

```python
x = [1, 2, 3]
y = [10, 20, 30]

result = map(lambda a, b: a + b, x, y)
print(list(result))
```

**Output:**
```
[11, 22, 33]
```

#### **2.2 Mapping with Complex Conditions**

```python
numbers = [4, 9, 16, 25]
result = map(lambda x: x ** 0.5 if x % 2 == 0 else x, numbers)
print(list(result))
```

**Output:**
```
[2.0, 9, 4.0, 25]
```

#### **2.3 Mapping Custom Functions**

```python
def double(x):
    return x * 2

numbers = [1, 2, 3, 4]
result = map(double, numbers)
print(list(result))
```

**Output:**
```
[2, 4, 6, 8]
```

---

### **Exercise 2:**

1. Create a list of strings and use `map()` to convert all strings to lowercase.
2. Create a function that adds 10 to a number and apply it to a list of numbers using `map()`.

---

## **3. `filter()` in Python**

### **Theory & Concept:**
`filter()` allows you to filter elements from an iterable based on a condition provided by a function. It returns a **filter object**, which can be converted into a list, tuple, or any other iterable.

The key benefit of `filter()` is that it lets you apply boolean logic across an iterable to select specific elements.

### **Basic Syntax:**
```python
filter(function, iterable)
```

- `function`: A function that returns either `True` or `False` for each element.
- `iterable`: An iterable object (list, tuple, etc.).

---

### **Basic Example:**

```python
numbers = [1, 2, 3, 4]
result = filter(lambda x: x % 2 == 0, numbers)
print(list(result))
```
**Output:**
```
[2, 4]
```

---

### **Advanced Use Cases:**

#### **3.1 Filtering Even and Odd Numbers:**

```python
numbers = [1, 2, 3, 4, 5, 6]
evens = filter(lambda x: x % 2 == 0, numbers)
odds = filter(lambda x: x % 2 != 0, numbers)

print(list(evens))  # [2, 4, 6]
print(list(odds))   # [1, 3, 5]
```

#### **3.2 Filtering Data Structures:**

```python
students = [
    {"name": "John", "age": 20, "grade": "A"},
    {"name": "Jane", "age": 22, "grade": "B"},
    {"name": "Doe", "age": 21, "grade": "A"}
]

filtered_students = filter(lambda x: x["grade"] == "A", students)
for student in filtered_students:
    print(student["name"])
```

**Output:**
```
John
Doe
```

---

### **Exercise 3:**

1. Given a list of strings, filter out all the strings that contain the letter 'a'.
2. Create a filter to find all numbers greater than 10 in a given list.

---

## **4. `reduce()` in Python**

### **Theory & Concept:**
`reduce()` from the `functools` module applies a binary function (a function that takes two arguments) cumulatively to the items of an iterable, reducing the iterable to a single value.

### **Basic Syntax:**
```python
from functools import reduce
reduce(function, iterable, [initializer])
```

- `function`: A function that takes two arguments.
- `iterable`: An iterable object (list, tuple, etc.).
- `initializer` (optional): An initial value to start the accumulation.

---

### **Basic Example:**

```python
from functools import reduce

numbers = [1, 2, 3, 4]
result = reduce(lambda x, y: x + y, numbers)
print(result)
```

**Output:**
```
10
```

---

### **Advanced Use Cases:**

#### **4.1 String Concatenation:**

```python
words = ["Hello", "world", "from", "Python"]
result = reduce(lambda x, y: x + " " + y, words)
print(result)
```

**Output:**
```
Hello world from Python
```

#### **4.2 Calculating Product of Numbers:**

```python
numbers = [1, 2, 3

, 4]
result = reduce(lambda x, y: x * y, numbers)
print(result)
```

**Output:**
```
24
```

---

### **Exercise 4:**

1. Use `reduce()` to find the **maximum** value in a list of numbers.
2. Use `reduce()` to concatenate a list of strings into a single sentence.

---

## **5. `lambda` Functions in Python**

### **Theory & Concept:**
A `lambda` function is a small anonymous function defined with the `lambda` keyword. It can take any number of arguments but can only have one expression.

### **Basic Syntax:**
```python
lambda arguments: expression
```

---

### **Basic Example:**

```python
add = lambda a, b: a + b
print(add(2, 3))
```

**Output:**
```
5
```

---

### **Advanced Use Cases:**

#### **5.1 Lambda with Higher-Order Functions:**

```python
numbers = [1, 2, 3, 4, 5]
result = map(lambda x: x * 2, numbers)
print(list(result))
```

#### **5.2 Lambda with Sorting:**

```python
people = [{"name": "Alice", "age": 30}, {"name": "Bob", "age": 25}]
sorted_people = sorted(people, key=lambda x: x["age"])
print(sorted_people)
```

**Output:**
```
[{'name': 'Bob', 'age': 25}, {'name': 'Alice', 'age': 30}]
```

---

### **Exercise 5:**

1. Write a lambda function that finds the square of a number.
2. Use a lambda function to sort a list of tuples based on the second element.

---

## **6. `match-case` (Pattern Matching)**

### **Theory & Concept:**
The `match-case` statement in Python 3.10 allows you to match complex data structures with a concise and readable syntax. It is much cleaner and easier to understand than traditional `if-elif-else` statements.

### **Basic Syntax:**
```python
match value:
    case pattern1:
        # Action for pattern1
    case pattern2:
        # Action for pattern2
    case _:
        # Default case
```

---

### **Basic Example:**

```python
def number_type(x):
    match x:
        case 0:
            return "Zero"
        case 1 | 2 | 3:
            return "Small number"
        case _:
            return "Large number"

print(number_type(3))
```

**Output:**
```
Small number
```

---

### **Advanced Use Cases:**

#### **6.1 Matching Types:**

```python
def check_data_type(value):
    match value:
        case int():
            print("This is an integer.")
        case str():
            print("This is a string.")
        case _:
            print("This is an unknown type.")

check_data_type(42)
```

**Output:**
```
This is an integer.
```

#### **6.2 Matching Data Structures:**

```python
data = {"name": "Alice", "age": 30}

match data:
    case {"name": name, "age": age}:
        print(f"Name: {name}, Age: {age}")
    case _:
        print("No match.")
```

**Output:**
```
Name: Alice, Age: 30
```

---

### **Exercise 6:**

1. Write a function that matches a string and returns the category (short, medium, long) based on length.
2. Match a list of numbers and print whether they are odd or even.

-----------

<p align="center"> <a href="./Day02.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day04.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

---------------
