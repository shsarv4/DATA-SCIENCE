
<h1 align="center">🌿 30 Days of Python 🌿</h1>
<p align="center">
  <a href="./Day20.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  
  <a href="./Day22.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a>
</p>

# Day 21: Polymorphism in Python – One Interface, Many Forms

1. [Vid 1](https://www.youtube.com/watch?v=j0Aq44Pze-w&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=67)
2. [Vid 2](https://www.youtube.com/watch?v=VGyDqWkzpCM&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=68)
3. [Vid 3](https://www.youtube.com/watch?v=2vPy4RDb3v4&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=69)

---

## 🎯 Objectives

By the end of this lesson, you will:

* Understand **what polymorphism means** in OOP.  
* Learn how Python achieves polymorphism through **dynamic typing**.  
* Explore **method overriding**, **method overloading**, and **operator overloading**.  
* Use **abstract classes** and **interfaces** to enforce polymorphism.  
* Build a real-world **mini project** to connect all the concepts.

---

## 1. What is Polymorphism?

**Polymorphism** comes from Greek words:
> *poly* → many, and *morph* → form.  
> Hence, **"many forms"**.

In programming, **polymorphism allows the same interface (method or operator) to behave differently** based on the object that is calling it.

📌 **Key idea:**
> Different classes can implement the same method name, but each behaves in its own way.

### Real-world Analogy

Imagine the word **“speak”**:
- A **dog** barks 🐶  
- A **cat** meows 🐱  
- A **cow** moos 🐮  

Same action — **different outcomes**.

---

## 2. Why Polymorphism Matters

Polymorphism brings **flexibility** and **scalability** to your code.

Without polymorphism, you might write code like this:

```python
if animal_type == "dog":
    bark()
elif animal_type == "cat":
    meow()
````

With polymorphism, you just call:

```python
animal.speak()
```

…and Python automatically calls the correct version based on the object’s type.

✅ **Benefits:**

* Reduces code complexity
* Makes code more extensible (easy to add new types)
* Supports *“Open/Closed Principle”* → open for extension, closed for modification

---

## 3. Method Polymorphism

This is the simplest and most common form of polymorphism.

Different classes can have methods with the same name and purpose but different implementations.

```python
class Dog:
    def speak(self):
        print("Woof!")

class Cat:
    def speak(self):
        print("Meow!")

class Cow:
    def speak(self):
        print("Moo!")

for animal in [Dog(), Cat(), Cow()]:
    animal.speak()
```

📌 Output:

```
Woof!
Meow!
Moo!
```

👉 Python doesn’t care *what type* of object it is — as long as it has the `speak()` method.
This is called **Duck Typing**:

> “If it walks like a duck and quacks like a duck, it’s a duck.”

---

## 4. Polymorphism through Inheritance (Method Overriding)

A **child class** can redefine a method inherited from its **parent class**.

```python
class Vehicle:
    def move(self):
        print("Vehicle is moving")

class Car(Vehicle):
    def move(self):   # overriding
        print("Car is driving")

class Boat(Vehicle):
    def move(self):
        print("Boat is sailing")

for v in [Vehicle(), Car(), Boat()]:
    v.move()
```

📌 Output:

```
Vehicle is moving
Car is driving
Boat is sailing
```

### How it Works

When we call `v.move()`, Python looks for the `move()` method:

1. First in the object’s own class
2. Then in its parent class (if not found)
3. Then up the inheritance chain until `object`

This lookup process is controlled by the **Method Resolution Order (MRO)**.

---

## 5. Function Polymorphism (Duck Typing)

You can write a function that works with multiple types of objects as long as they implement a required behavior.

```python
class Bird:
    def fly(self):
        print("Bird is flying")

class Airplane:
    def fly(self):
        print("Airplane is soaring")

class Fish:
    def swim(self):
        print("Fish is swimming")

def flight_test(entity):
    entity.fly()   # works for anything that has fly()

for e in [Bird(), Airplane()]:
    flight_test(e)
```

📌 Output:

```
Bird is flying
Airplane is soaring
```

⚠️ If you pass an object without a `fly()` method (like `Fish()`), Python will raise an `AttributeError`.
That’s the trade-off of **dynamic typing** — flexible but not type-safe.

---

## 6. Method Overloading (Python’s Way)

In many languages, you can have multiple methods with the same name but different argument lists.

Python does **not** support this natively.
However, we can achieve similar behavior using **default arguments** or `*args`.

```python
class Calculator:
    def add(self, a, b=0, c=0):
        return a + b + c

calc = Calculator()
print(calc.add(5))          # 5
print(calc.add(5, 10))      # 15
print(calc.add(5, 10, 20))  # 35
```

📌 Python determines behavior *at runtime* based on the number or type of arguments.

---

## 7. Operator Overloading (Magic Methods)

Python allows you to redefine how operators work for user-defined objects using **special methods** like `__add__`, `__sub__`, etc.

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Point(self.x + other.x, self.y + other.y)

    def __str__(self):
        return f"({self.x}, {self.y})"

p1 = Point(2, 3)
p2 = Point(4, 5)
print(p1 + p2)
```

📌 Output:

```
(6, 8)
```

### Common Magic Methods

| Operation      | Method                       | Example           |
| -------------- | ---------------------------- | ----------------- |
| Addition       | `__add__`                    | `a + b`           |
| Subtraction    | `__sub__`                    | `a - b`           |
| Multiplication | `__mul__`                    | `a * b`           |
| Comparison     | `__eq__`, `__lt__`, `__gt__` | `a == b`, `a < b` |

---

## 8. Abstract Classes – Enforcing Polymorphism

Sometimes we want to **force** subclasses to implement certain methods.
Python provides the `abc` module for this.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, w, h):
        self.w = w
        self.h = h

    def area(self):
        return self.w * self.h

class Circle(Shape):
    def __init__(self, r):
        self.r = r

    def area(self):
        return 3.14 * self.r * self.r

for shape in [Rectangle(4, 5), Circle(3)]:
    print(shape.area())
```

📌 Output:

```
20
28.26
```

💡 **Note:**
You cannot create an object of an abstract class directly.
It exists to define a *common interface* for all its children.

---

## 9. Real-World Example – Payment Gateway

```python
class Payment:
    def pay(self, amount):
        raise NotImplementedError("Subclass must implement this method")

class CreditCardPayment(Payment):
    def pay(self, amount):
        print(f"Paid ₹{amount} using Credit Card")

class PayPalPayment(Payment):
    def pay(self, amount):
        print(f"Paid ₹{amount} via PayPal")

class UpiPayment(Payment):
    def pay(self, amount):
        print(f"Paid ₹{amount} using UPI")

payments = [CreditCardPayment(), PayPalPayment(), UpiPayment()]

for p in payments:
    p.pay(500)
```

📌 Output:

```
Paid ₹500 using Credit Card
Paid ₹500 via PayPal
Paid ₹500 using UPI
```

👉 Same `pay()` method — three different implementations!

---

## 10. Mini Project: Animal Sound Simulator 🎵

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def sound(self):
        pass

class Dog(Animal):
    def sound(self):
        return "Woof!"

class Cat(Animal):
    def sound(self):
        return "Meow!"

class Cow(Animal):
    def sound(self):
        return "Moo!"

animals = [Dog(), Cat(), Cow()]
for a in animals:
    print(f"{a.__class__.__name__} → {a.sound()}")
```

📌 Output:

```
Dog → Woof!
Cat → Meow!
Cow → Moo!
```

This is **polymorphism in action**:
Same method (`sound()`), different behaviors depending on the class.

---

## 11. Reflection Questions

1. What does *polymorphism* mean in simple terms?
2. How does Python achieve polymorphism without strict typing?
3. Why is polymorphism important in large projects?
4. What is the difference between **method overriding** and **operator overloading**?
5. Why can’t we instantiate abstract classes directly?

---

## 12. Recap Quiz

1. Create an abstract class `Shape` with subclasses `Square`, `Circle`, and `Triangle`. Each should implement an `area()` method.
2. Implement operator overloading for a `Vector` class that supports addition (`+`) and magnitude comparison (`>`).
3. Write a function `make_it_move()` that accepts multiple vehicle types (Car, Plane, Ship) and calls their `move()` methods polymorphically.

---

<p align="center">
  <a href="./Day20.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  
  <a href="./Day22.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a>
</p>
```
