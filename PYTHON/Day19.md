<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center">
  <a href="./Day19.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day21.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a>
</p>

# Constructor in Python

1. [Vid 1](https://www.youtube.com/watch?v=12HRkYld22c&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=59&ab_channel=CodeWithHarry)

## 🎯 Objectives

By the end of this lesson, you will:

* Understand what a constructor is and why it exists.
* Learn the difference between `__new__` and `__init__`.
* Master default, parameterized, and overloaded constructors.
* Explore advanced patterns like alternative constructors (`@classmethod`).
* Understand constructor chaining with `super()`.
* Recognize pitfalls (mutable defaults, misuse of `__init__`).
* Build hands-on mini projects to reinforce concepts.

---

## 1. What is a Constructor?

A **constructor** is a special method that runs automatically when you create an object.

* It prepares the object for use.
* It initializes its attributes.

🔑 In Python, **object creation has 2 steps**:

1. **`__new__`** → Creates the object in memory.
2. **`__init__`** → Initializes the object with values.

📌 Analogy: Building a house

* `__new__` = laying the foundation (house exists but is empty).
* `__init__` = furnishing the rooms (house is ready to live in).

---

## 2. The `__init__()` Constructor

```python
class Person:
    def __init__(self, name, age):
        print("Initializing a new Person object...")
        self.name = name
        self.age = age

p1 = Person("Swati", 25)
print(p1.name, p1.age)
```

**Output:**

```
Initializing a new Person object...
Swati 25
```

---

## 3. Types of Constructors

### 3.1 Default Constructor

```python
class Car:
    def __init__(self):
        self.brand = "Toyota"
        self.model = "Camry"

c = Car()
print(c.brand, c.model)  # Toyota Camry
```

### 3.2 Parameterized Constructor

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

c1 = Car("Toyota", "Camry")
c2 = Car("Honda", "Civic")
print(c1.brand, c2.brand)  # Toyota Honda
```

### 3.3 Constructor with Default Arguments

```python
class Laptop:
    def __init__(self, brand="Dell", processor="i5"):
        self.brand = brand
        self.processor = processor

l1 = Laptop()
l2 = Laptop("HP", "i7")
print(l1.brand, l2.processor)  # Dell i7
```

---

## 4. Constructor Overloading (Python Way)

Python doesn’t support multiple `__init__` definitions. Instead:

* Use **default arguments**.
* Or use **`*args` and `**kwargs`**.

```python
class Person:
    def __init__(self, *args):
        if len(args) == 2:
            self.name, self.age = args
        else:
            self.name, self.age = "Unknown", 0

p1 = Person("Swati", 25)
p2 = Person()
print(p1.name, p2.name)  # Swati Unknown
```

---

## 5. Alternative Constructors with `@classmethod`

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def from_string(cls, data):
        name, age = data.split(",")
        return cls(name, int(age))

p1 = Person("Swati", 25)
p2 = Person.from_string("Amit,30")

print(p1.name, p2.name)  # Swati Amit
```

📊 **Comparison Table**

| Constructor Type | Example                          | Use Case                             |
| ---------------- | -------------------------------- | ------------------------------------ |
| `__init__`       | `Person("Swati", 25)`            | Normal initialization                |
| `@classmethod`   | `Person.from_string("Swati,25")` | Alternative ways of creating objects |

---

## 6. Constructor Chaining with `super()`

Used in inheritance to call parent constructor.

```python
class Vehicle:
    def __init__(self, brand):
        self.brand = brand

class Car(Vehicle):
    def __init__(self, brand, model):
        super().__init__(brand)  # parent constructor
        self.model = model

c = Car("Toyota", "Camry")
print(c.brand, c.model)  # Toyota Camry
```

📌 **Diagram:**

```
Car() → Car.__init__ → super() → Vehicle.__init__
```

---

## 7. The `__new__()` Constructor

* Responsible for **creating** the object in memory.
* Rarely overridden, but used for **Singletons** or **immutables**.

```python
class Singleton:
    _instance = None
    def __new__(cls, *args, **kwargs):
        if not cls._instance:
            cls._instance = super().__new__(cls)
        return cls._instance

s1 = Singleton()
s2 = Singleton()
print(s1 is s2)  # True
```

---

## 8. Destructor: `__del__()`

Runs when object is about to be destroyed.

```python
class Demo:
    def __init__(self):
        print("Object created.")
    def __del__(self):
        print("Object destroyed.")

obj = Demo()
del obj
```

⚠️ Don’t rely too much on `__del__`. Garbage collection may skip it.

---

## 9. Common Pitfalls

### 9.1 Mutable Default Arguments

```python
class Student:
    def __init__(self, name, subjects=[]):  # BAD
        self.name = name
        self.subjects = subjects
```

All instances share the same list 😱

✅ Fix:

```python
class Student:
    def __init__(self, name, subjects=None):
        self.name = name
        self.subjects = subjects if subjects else []
```

### 9.2 Forgetting `self`

```python
class Person:
    def __init__(name):  # ❌ Missing self
        self.name = name
```

---

## 10. Mini Project: Employee Management

```python
class Employee:
    def __init__(self, name, salary, position="Intern"):
        self.name = name
        self.salary = salary
        self.position = position

    @classmethod
    def from_string(cls, data):
        name, salary, position = data.split(",")
        return cls(name, float(salary), position)

    def display(self):
        print(f"{self.name} - {self.position} - ${self.salary}")

# Using normal constructor
e1 = Employee("Swati", 50000, "Developer")

# Using alternative constructor
e2 = Employee.from_string("Amit,60000,Manager")

e1.display()
e2.display()
```

---

## 11. Reflection Questions

1. What’s the difference between `__new__` and `__init__`?
2. Why doesn’t Python support constructor overloading directly?
3. When would you prefer a classmethod constructor?
4. Why is using mutable default arguments dangerous?

---

## 12. Recap Quiz

1. Write a class `Product` with attributes `name`, `price`, and `discount=0`. Add a method `final_price()` to return price after discount.
2. Create a singleton class using `__new__`.
3. Demonstrate constructor chaining with `super()`.

---


<p align="center"> <a href="./Day19.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day21.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>
