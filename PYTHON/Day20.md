<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center">
  <a href="./Day19.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day21.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a>
</p>


# Day 20: Inheritance in Python – Reusing and Extending Classes

---

## 🎯 Objectives

By the end of this lesson, you will:

* Understand the concept of **inheritance** and why it matters in OOP.
* Learn different types of inheritance in Python.
* Master constructor chaining using `super()`.
* Explore **method overriding** and `super()` usage.
* Understand **multiple inheritance** and the **MRO (Method Resolution Order)**.
* Learn about `isinstance()`, `issubclass()`.
* Build real-world examples and a mini-project.

---

## 1. What is Inheritance?

Inheritance allows a **child class** (subclass) to reuse and extend the functionality of a **parent class** (superclass).

📌 Analogy:

* Parent class = *Blueprint for general vehicles*.
* Child class = *Specialized blueprint for cars, bikes, trucks*.

---

## 2. Basic Inheritance

```python
class Animal:
    def speak(self):
        print("Animal makes a sound")

class Dog(Animal):
    def bark(self):
        print("Woof! Woof!")

d = Dog()
d.speak()   # Inherited
d.bark()    # Defined in Dog
```

---

## 3. The `super()` Keyword

Used to call parent class methods (especially constructors).

```python
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)   # calls Animal’s __init__
        self.breed = breed

d = Dog("Buddy", "Labrador")
print(d.name, d.breed)  # Buddy Labrador
```

📌 **Diagram:**

```
Dog() → Dog.__init__() → super() → Animal.__init__()
```

---

## 4. Method Overriding

Child class can redefine a method from parent class.

```python
class Animal:
    def speak(self):
        print("Some generic sound")

class Dog(Animal):
    def speak(self):   # override
        print("Woof!")

a = Animal()
d = Dog()
a.speak()  # Some generic sound
d.speak()  # Woof!
```

---

## 5. Types of Inheritance in Python

### 5.1 Single Inheritance

```python
class A:
    pass
class B(A):
    pass
```

### 5.2 Multilevel Inheritance

```python
class A:
    pass
class B(A):
    pass
class C(B):
    pass
```

### 5.3 Hierarchical Inheritance

```python
class A:
    pass
class B(A):
    pass
class C(A):
    pass
```

### 5.4 Multiple Inheritance

```python
class A:
    def feature(self):
        print("Feature from A")

class B:
    def feature(self):
        print("Feature from B")

class C(A, B):
    pass

c = C()
c.feature()  # Feature from A (MRO decides)
```

📌 **Diagram (Multiple Inheritance)**

```
    A       B
     \     /
      \   /
        C
```

---

## 6. Method Resolution Order (MRO)

Python uses **C3 linearization** (depth-first, left-to-right).

```python
class A: pass
class B(A): pass
class C(A): pass
class D(B, C): pass

print(D.mro())
```

**Output:**

```
[<class '__main__.D'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class 'object'>]
```

📌 **Diagram (MRO flow for D(B, C))**

```
D → B → C → A → object
```

---

## 7. Useful Functions

* `isinstance(obj, Class)` → Checks if object belongs to class or subclass.
* `issubclass(Child, Parent)` → Checks if a class is a subclass of another.

```python
print(isinstance(d, Dog))     # True
print(isinstance(d, Animal))  # True
print(issubclass(Dog, Animal)) # True
```

---

## 8. Real-World Example

```python
class Vehicle:
    def __init__(self, brand):
        self.brand = brand

    def drive(self):
        print(f"{self.brand} vehicle is moving")

class Car(Vehicle):
    def __init__(self, brand, model):
        super().__init__(brand)
        self.model = model

    def drive(self):  # override
        print(f"{self.brand} {self.model} car is driving")

v = Vehicle("Generic")
c = Car("Toyota", "Camry")

v.drive()
c.drive()
```

---

## 9. Mini Project: School Management

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

class Student(Person):
    def __init__(self, name, age, grade):
        super().__init__(name, age)
        self.grade = grade

    def info(self):
        print(f"Student: {self.name}, Grade: {self.grade}")

class Teacher(Person):
    def __init__(self, name, age, subject):
        super().__init__(name, age)
        self.subject = subject

    def info(self):
        print(f"Teacher: {self.name}, Subject: {self.subject}")

s = Student("Swati", 15, "10th")
t = Teacher("Mr. Amit", 40, "Math")

s.info()
t.info()
```

---

## 10. Reflection Questions

1. Why do we use `super()` instead of directly calling parent’s method?
2. How does Python decide which method to run in multiple inheritance?
3. Can a child class access private attributes of parent class? Why or why not?
4. What’s the difference between overriding and overloading?

---

## 11. Recap Quiz

1. Create a class hierarchy: `Shape` → `Rectangle`, `Circle`. Each should implement an `area()` method.
2. Demonstrate multiple inheritance with `Artist` and `Engineer` → `Designer`.
3. Show how `isinstance()` and `issubclass()` work with your classes.

---
<p align="center"> <a href="./Day19.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day21.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>
