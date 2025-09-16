<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day17.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day19.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

## **Day 18: Better Understanding of Classes & Objects**

### **Objective**

By the end of Day 18 you will:

* Have a complete, self-contained understanding of what classes and objects are in Python.
* Know every common attribute type, method type, and how Python stores them (`__dict__`, namespaces).
* Understand how methods are looked up and bound at runtime.
* Master object lifecycle: `__new__`, `__init__`, destruction and garbage collection basics.
* Be fluent with composition, attribute shadowing, mutable traps, and best class-design practices.
* Be able to inspect, debug and reason about objects in real-world code.

---

### **Table of contents**

1. Introduction & mental model
2. Class vs object vs instance — under the hood
3. Attribute deep dive: instance, class, dynamic, and shadowing
4. Methods — instance, class, static; binding & internals
5. Namespaces and attribute lookup order (with examples)
6. Object lifecycle — `__new__`, `__init__`, `__del__`, GC
7. Memory & object identity (id, reference counting, weakref)
8. Composition vs Inheritance — when to use which
9. Descriptors & a gentle intro to `@property`
10. Mutable vs immutable attributes, shallow vs deep copy
11. Inspecting and debugging objects (`dir`, `vars`, `inspect`)
12. Best practices, anti-patterns, and design tips
13. Mini-projects and exercises with solutions
14. Reflection questions & recap quiz

---

## 1. Introduction & mental model

A **class** is a blueprint — it defines *structure* (attributes) and *behaviour* (methods). An **object** is a concrete entity built from that blueprint. But in Python, it's useful to go a layer deeper: classes themselves are objects (instances of `type`), and attributes/methods live in *namespaces* (dictionaries) that Python uses at runtime to resolve names.

Think of it like this:

* The **class** is a blueprint in a workshop (a file of instructions, stored once).
* Each **object** is a manufactured product — it has parts (instance attributes) that can differ from product to product.
* The **class namespace** is the shelf where shared parts (class attributes & methods) are kept.

We’ll now translate that metaphor into concrete code and show how Python does it under the hood.

---

## 2. Class vs object vs instance — under the hood

```python
class Car:
    wheels = 4  # class attribute (shared)

    def __init__(self, brand, model):
        self.brand = brand  # instance attribute (per object)
        self.model = model

c1 = Car('Toyota', 'Camry')
c2 = Car('Honda', 'Civic')

print(type(Car))   # <class 'type'>  (classes are objects)
print(type(c1))    # <class '__main__.Car'>
print(isinstance(c1, Car))  # True
print(c1.__class__ is Car)  # True

print('c1 id:', id(c1))
print('c2 id:', id(c2))
```

**Explanation:**

* `Car` itself is an object (an instance of `type`), which is why you can pass classes around, attach attributes to them, or create subclasses dynamically.
* Each `Car` instance has its own identity (memory address shown by `id()`), and its own `__dict__` that stores instance attributes.

---

## 3. Attribute deep dive

### 3.1 Instance attributes

* Created per object, usually inside `__init__` using `self`.
* Stored in the instance namespace: `instance.__dict__`.

```python
class Person:
    def __init__(self, name):
        self.name = name

p = Person('Swati')
print(p.__dict__)   # {'name': 'Swati'}
```

**When to use:** Use instance attributes for data unique to each object.

---

### 3.2 Class attributes

* Defined in the class body. Shared across all instances unless shadowed.
* Stored in the class namespace: `ClassName.__dict__`.

```python
class Student:
    school = 'ABC High'

s1 = Student('Amit')
print(Student.__dict__['school'])  # 'ABC High'
print(s1.school)  # accesses class attribute via instance lookup
```

**When to use:** Use class attributes for properties common to all instances (constants, configuration defaults, caches).

---

### 3.3 Dynamic (runtime) attributes

* Python lets you add attributes to instances (and classes) at runtime.

```python
s1.grade = 'A'
print(s1.__dict__)  # now includes 'grade'

Student.version = 1.2  # add class attribute at runtime
```

**Caution:** Dynamic attributes can be powerful but reduce predictability. Use sparingly in production code.

---

### 3.4 Shadowing and lookup rules

* If an instance has an attribute with the same name as a class attribute, the instance attribute *shadows* the class attribute.

```python
class Demo:
    value = 10

d = Demo()
print(d.value)  # 10 (comes from class)

d.value = 99    # create instance attribute shadowing the class attribute
print(d.value)  # 99 (instance)
print(Demo.value)  # 10 (class still unchanged)
```

**Why this matters:** Accidentally shadowing can cause confusing bugs. Inspect `__dict__` when debugging.

---

### 3.5 Mutable class attributes — the common trap

```python
class Bag:
    items = []  # BAD: shared mutable object

    def add(self, item):
        self.items.append(item)

b1 = Bag()
b2 = Bag()
b1.add('apple')
print(b2.items)  # ['apple'] — unexpected shared state
```

**Fix** — initialize mutable attributes per-instance inside `__init__`:

```python
class Bag:
    def __init__(self):
        self.items = []  # unique list per instance
```

**Rule of thumb:** Never use mutable objects as class attributes unless you intentionally want shared state.

---

## 4. Methods: instance, class, static — binding & internals

### 4.1 Instance methods (normal methods)

```python
class Rectangle:
    def __init__(self, l, w):
        self.l = l
        self.w = w

    def area(self):  # instance method
        return self.l * self.w

r = Rectangle(5, 3)
print(r.area())  # 15
```

**Binding detail (important):**

* A function defined in a class becomes a **descriptor**.
* Accessing it via an instance returns a *bound method* where `self` is already bound.

```python
print(Rectangle.area)        # function object (unbound in Python 3 it's just function)
print(r.area)  # <bound method Rectangle.area of <__main__.Rectangle object at 0x...>>
```

Under the hood, the function implements `__get__` which returns a `types.MethodType` when accessed from an instance. This is why `r.area()` automatically gets `r` as the first argument.

---

### 4.2 Class methods (`@classmethod`)

* Receive the class `cls` as the first argument instead of `self`.
* Useful for factory methods or when you need to modify class-level data.

```python
class Circle:
    pi = 3.14

    @classmethod
    def set_pi(cls, value):
        cls.pi = value

Circle.set_pi(3.14159)
print(Circle.pi)
```

**Example — alternative constructor**:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def from_string(cls, s):
        name, age = s.split(',')
        return cls(name.strip(), int(age))

p = Person.from_string('Swati, 25')
```

---

### 4.3 Static methods (`@staticmethod`)

* Do not receive an implicit first argument.
* Behave like regular functions placed in a class namespace for organization.

```python
class Math:
    @staticmethod
    def add(a, b):
        return a + b

print(Math.add(2,3))
```

**When to use:** Utility functions related to the class but not depending on class or instance state.

---

### 4.4 Method resolution & `__get__` — short internals

* Functions defined in the class implement the descriptor protocol (`__get__`).
* When accessed through an instance, `function.__get__(instance, owner)` returns a bound method with `instance` bound.
* When accessed through the class, it returns the raw function.

This explains why methods behave differently when called from the instance vs the class.

---

## 5. Namespaces and attribute lookup order

When you reference `obj.attr`, Python follows this lookup order:

1. `obj.__dict__` (instance namespace)
2. `obj.__class__.__dict__` (class namespace)
3. Follow the MRO of parent classes (for inheritance)
4. `object` class namespace

Example that demonstrates lookup order:

```python
class A:
    x = 'A'

class B(A):
    pass

b = B()
print(b.x)  # 'A' found in parent class A

b.x = 'B-instance'
print(b.x)  # 'B-instance' (instance attribute shadows class attribute)
```

Use `vars(obj)` (or `obj.__dict__`) and `vars(Class)` to inspect namespaces.

---

## 6. Object lifecycle — `__new__`, `__init__`, `__del__`

### 6.1 `__new__` — low-level allocation

* `__new__` is the method that actually **creates** and returns a new instance. It’s called before `__init__`.
* It's useful when subclassing immutable built-ins (like `str`, `tuple`) or implementing singletons.

```python
class MyInt(int):
    def __new__(cls, value):
        print('Creating instance')
        return super().__new__(cls, value)

n = MyInt(5)  # 'Creating instance'
```

**Singleton example using `__new__`:**

```python
class Singleton:
    _instance = None

    def __new__(cls, *args, **kwargs):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance

s1 = Singleton()
s2 = Singleton()
print(s1 is s2)  # True
```

### 6.2 `__init__` — initialization

* Called after `__new__` with the created instance as `self`.
* Good place to set up instance attributes.

### 6.3 `__del__` — destructor

* Called when the object is about to be destroyed; **not guaranteed** to run immediately when you `del` an object (GC dependent).

```python
class Demo:
    def __del__(self):
        print('Destroyed')

obj = Demo()
del obj  # may print 'Destroyed' immediately in CPython due to ref counting, but not reliable cross-implementations
```

**Advice:** Do not rely on `__del__` for critical cleanup. Use context managers (`with` / `__enter__` / `__exit__`) or explicit `close()` methods.

---

## 7. Memory & object identity

* `id(obj)` returns an integer unique during the object's lifetime (address in CPython).
* CPython uses **reference counting** + cyclic garbage collector.
* If you want a weak reference (doesn’t increase reference count), use the `weakref` module — useful for caches.

```python
import weakref

class Data: pass

d = Data()
w = weakref.ref(d)
print(w())  # <__main__.Data object ...>
d = None
print(w())  # None (object collected)
```

**Note:** Understanding identity (`is`) vs equality (`==`) is important when implementing `__eq__`.

---

## 8. Composition vs Inheritance — design guidance

* **Inheritance (IS-A)**: appropriate when child *is a* specialized form of parent (e.g., `Car` is a `Vehicle`).
* **Composition (HAS-A)**: preferred when building larger objects from smaller parts; it promotes loose coupling.

**Example (composition):**

```python
class Engine:
    def start(self):
        print('engine running')

class Car:
    def __init__(self, engine):
        self.engine = engine  # composition

    def drive(self):
        self.engine.start()
        print('car moving')

car = Car(Engine())
car.drive()
```

**Guideline:** Favor composition when you want more flexible code that’s easy to test and change.

---

## 9. Descriptors & `@property` (gentle introduction)

A **descriptor** is an object with any of `__get__`, `__set__`, or `__delete__` methods. Functions (methods) and `property` are descriptors under the hood.

### 9.1 `@property` example

```python
class Person:
    def __init__(self, name, age):
        self._name = name
        self._age = age

    @property
    def age(self):
        return self._age

    @age.setter
    def age(self, value):
        if value < 0:
            raise ValueError('age cannot be negative')
        self._age = value

p = Person('Swati', 25)
print(p.age)
p.age = 30
```

### 9.2 Custom descriptor example (type-enforcing)

```python
class Typed:
    def __init__(self, name, type_):
        self.name = name
        self.type_ = type_

    def __get__(self, instance, owner):
        if instance is None:
            return self
        return instance.__dict__[self.name]

    def __set__(self, instance, value):
        if not isinstance(value, self.type_):
            raise TypeError(f'{self.name} must be {self.type_}')
        instance.__dict__[self.name] = value

class Point:
    x = Typed('x', int)
    y = Typed('y', int)

    def __init__(self, x, y):
        self.x = x
        self.y = y

p = Point(1,2)
# p.x = 1.5  # would raise TypeError
```

**Why this matters:** Understanding descriptors helps you grasp how `@property` and bound methods work internally.

---

## 10. Mutable vs Immutable attributes; shallow & deep copy

### 10.1 Mutable vs Immutable

* Immutable: `int`, `str`, `tuple` — safe to share as default class attributes conceptually.
* Mutable: `list`, `dict`, `set` — avoid as class defaults.

### 10.2 Shallow vs deep copy

```python
import copy

class Node:
    def __init__(self, data):
        self.data = data

n1 = Node([1,2])
n2 = copy.copy(n1)       # shallow copy; n2.data is same list object
n3 = copy.deepcopy(n1)   # deep copy; n3.data is a new list

n1.data.append(3)
print(n2.data)  # affected (shallow)
print(n3.data)  # not affected (deep)
```

**When to use which:** copy shallowly when you want a new container wrapper but shared nested objects are OK; deep copy when you need a fully independent object graph.

---

## 11. Inspecting and debugging objects

Useful built-ins and modules:

* `vars(obj)` or `obj.__dict__` — instance attributes
* `vars(Class)` or `Class.__dict__` — class namespace
* `dir(obj)` — combined attributes (includes methods, descriptors)
* `getattr`, `setattr`, `hasattr`, `delattr`
* `inspect` module for signatures, source, and members

```python
import inspect
print(inspect.getsource(Person))
print(inspect.signature(Person.__init__))
```

---

## 12. Best practices and anti-patterns

**Do:**

* Keep classes small and focused (Single Responsibility Principle).
* Prefer composition over inheritance when behaviour can be delegated.
* Use `__repr__` (developer-friendly) and `__str__` (user-friendly) for meaningful string representations.
* Use `@classmethod` for alternative constructors (e.g., `from_dict`, `from_json`).

**Don't:**

* Use mutable default class attributes unintentionally.
* Rely on `__del__` for resource cleanup; prefer context managers.
* Overcomplicate with deep inheritance hierarchies (consider composition or interfaces/ABC instead).

**Naming and style:** Follow PEP8 (class names in `CamelCase`, methods and variables in `snake_case`).

---

## 13. Mini-projects — complete examples & solutions

### 13.1 BankAccount (robust)

```python
class BankAccount:
    bank_name = 'XYZ Bank'  # class attribute

    def __init__(self, acc_no, balance=0):
        self.acc_no = acc_no
        self.balance = balance

    def deposit(self, amount):
        if amount <= 0:
            raise ValueError('Deposit must be positive')
        self.balance += amount

    def withdraw(self, amount):
        if amount <= 0:
            raise ValueError('Withdraw must be positive')
        if amount > self.balance:
            raise ValueError('Insufficient funds')
        self.balance -= amount

    @classmethod
    def change_bank_name(cls, name):
        cls.bank_name = name

    @staticmethod
    def is_valid_amount(amount):
        return isinstance(amount, (int, float)) and amount > 0

# Usage
acc = BankAccount(123, 1000)
acc.deposit(200)
acc.withdraw(150)
print(acc.balance)  # 1050
BankAccount.change_bank_name('New Bank')
print(BankAccount.bank_name)
```

### 13.2 Library with composition & inspect features

```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

    def __repr__(self):
        return f"Book({self.title!r}, {self.author!r})"

class Library:
    def __init__(self, name):
        self.name = name
        self._books = []

    def add_book(self, book):
        if not isinstance(book, Book):
            raise TypeError('expected Book')
        self._books.append(book)

    def find_by_author(self, author):
        return [b for b in self._books if b.author == author]

lib = Library('City')
lib.add_book(Book('Python 101', 'Swati'))
lib.add_book(Book('ML Guide', 'Amit'))
print(lib.find_by_author('Swati'))
```

---

## 14. Exercises (with hints/answers)

1. **Attribute shadowing:** Create a class `Counter` with class attribute `count = 0`. Create two instances and modify `count` on one instance—what happens? (Hint: inspect `__dict__` and class attribute.)

**Answer summary:** Modifying instance `count` creates an instance attribute that shadows the class attribute; class attribute untouched.

2. **Method binding:** Print `MyClass.method` and `instance.method`. Notice types and explain why calling `instance.method()` passes `self` automatically.

**Answer summary:** `MyClass.method` is a function; `instance.method` is a bound method (descriptor returned a `MethodType`) with `self` bound.

3. **Mutable class trap:** Demonstrate the shared list bug and fix it by moving the list into `__init__`.

4. **Inspect:** Use `inspect.signature()` to print the signature of a method and explain parameters.

---

## Reflection Questions

1. How does Python decide where to look for `obj.attr`?
2. Why is `__new__` sometimes necessary for immutable types?
3. What are the trade-offs between class attributes and instance attributes?
4. Why should you prefer composition over deep inheritance?

---

## Recap Quiz

1. Implement a `Vector` class with `x`, `y`; make `__repr__` readable and implement `__add__`.
2. Create a `User` class with a `from_dict` `@classmethod` alternate constructor.
3. Show an example where mutable class attributes cause bugs and fix it.
4. Implement a small `Cache` class using `weakref` so stored values can be garbage collected when not used anywhere else.

---

<p align="center"> <a href="./Day17.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day19.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>


----------------
