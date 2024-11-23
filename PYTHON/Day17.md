<h1 align="center">🌱 30 Days of Python 🌱</h1>
<p align="center"> <a href="./Day16.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day18.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>



## **Day 17: Introduction to OOP, Classes, Objects, and Constructors**

### **Objective**
By the end of Day 17, You will:
1. Understand the fundamental principles of Object-Oriented Programming (OOP).
2. Be able to define and use classes and objects in Python.
3. Learn how constructors are used to initialize objects with dynamic data.
4. Grasp essential concepts like `self`, attributes, and methods.

### Vidoes
1. **[Video 1](https://www.youtube.com/watch?v=HQnoYzxOHMw&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=56&ab_channel=CodeWithHarry)**
2. **[Video 2](https://www.youtube.com/watch?v=a7baAGCBA9U&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=57&ab_channel=CodeWithHarry)**
3. **[Vid 3](https://www.youtube.com/watch?v=12HRkYld22c&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=58&ab_channel=CodeWithHarry)**
---

---

### **1. Detailed Introduction to Object-Oriented Programming (OOP)**

#### **1.1 What is OOP?**
- **Object-Oriented Programming (OOP)** is a programming paradigm that organizes code into **classes** and **objects**. Unlike procedural programming, which focuses on functions and sequences of tasks, OOP models real-world entities as objects.

---

#### **1.2 Key Principles of OOP**
1. **Encapsulation**:
   - Bundling data (attributes) and methods (functions) into a single unit (class).
   - Controls access to internal state using visibility modifiers (like `public`, `private`).
   - Benefits:
     - Protects the data.
     - Provides a controlled interface to interact with the data.

   **Example**:
   ```python
   class Account:
       def __init__(self, account_number, balance):
           self.__account_number = account_number  # Private attribute
           self.__balance = balance

       def deposit(self, amount):
           self.__balance += amount

       def get_balance(self):
           return self.__balance
   ```

   Here, the `__balance` attribute is protected, and the only way to modify or access it is through defined methods like `deposit()` or `get_balance()`.

---

2. **Inheritance**:
   - Mechanism to create a new class (child) from an existing class (parent).
   - Promotes code reuse.
   - Benefits:
     - Reduces redundancy.
     - Creates hierarchical relationships.

   **Real-World Example**:
   - A `Vehicle` class can have child classes like `Car` and `Bike` that inherit common attributes and methods but can also define their own specific behaviors.

---

3. **Polymorphism**:
   - Ability of different objects to respond to the same function call in different ways.
   - Achieved through **method overriding** or **method overloading**.

   **Example**:
   ```python
   class Animal:
       def speak(self):
           pass

   class Dog(Animal):
       def speak(self):
           return "Woof!"

   class Cat(Animal):
       def speak(self):
           return "Meow!"

   animals = [Dog(), Cat()]
   for animal in animals:
       print(animal.speak())
   ```

   **Output**:
   ```
   Woof!
   Meow!
   ```

---

4. **Abstraction**:
   - Hides implementation details and exposes only essential features.
   - Encourages focusing on "what an object does" rather than "how it does it."

   **Example**:
   - A `Car` object might provide a `drive()` method without exposing the complexities of the engine's internal workings.

---

#### **1.3 Why Use OOP?**
- **Modularity**: Classes and objects allow developers to break large programs into manageable parts.
- **Code Reusability**: Reuse existing classes through inheritance.
- **Flexibility**: Polymorphism allows extending and adapting programs with minimal changes.
- **Scalability**: Encapsulation ensures that data is secure and changes to one part of a program don’t affect others.

---

#### **1.4 Real-World Analogy**
- Imagine a **Car**:
  - **Attributes**: Color, brand, engine capacity.
  - **Behaviors** (Methods): Start, accelerate, brake.

  In OOP:
  - The **Car class** defines these attributes and behaviors.
  - A specific car (e.g., "Red Toyota Camry") is an **object** created using this class.

---

### **2. Classes and Objects in Python**

#### **2.1 What is a Class?**
- A **class** is a blueprint or template for creating objects. It defines attributes (data) and methods (behaviors) that the objects created from it will have.
  
- **Example**:
  ```python
  class Car:
      # Attributes
      wheels = 4
      engine = "V6"
      
      # Methods
      def start(self):
          print("The car has started.")
  ```

---

#### **2.2 What is an Object?**
- An **object** is an instance of a class. It represents a specific entity created using the class blueprint.

- **Example**:
  ```python
  my_car = Car()  # Object creation
  print(my_car.wheels)  # Accessing attributes
  my_car.start()  # Calling a method
  ```

  **Output**:
  ```
  4
  The car has started.
  ```

---

### **3. Methods in Classes**

#### **3.1 What are Methods?**
- **Methods** are functions defined inside a class. They define the behaviors of the objects created from the class.

#### **3.2 Example: Adding a Method**
```python
class Dog:
    def bark(self):
        print("Woof!")
        
my_dog = Dog()
my_dog.bark()
```

**Output**:
```
Woof!
```

---

### **4. The `self` Parameter**

#### **4.1 Understanding `self`**
- Represents the current instance of the class.
- Used to access attributes and methods of the object.

#### **4.2 Example of `self`**
```python
class Person:
    def greet(self):
        print(f"Hello, my name is {self.name}.")
        
person = Person()
person.name = "Swati"
person.greet()
```

**Output**:
```
Hello, my name is Swati.
```

---

### **5. Constructors in Python**

#### **5.1 What is a Constructor?**
- A **constructor** is a special method used to initialize the attributes of an object.
- In Python, the constructor method is `__init__()`.

#### **5.2 Example of a Constructor**
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def greet(self):
        print(f"Hi, I am {self.name}, and I am {self.age} years old.")
        
person = Person("Swati", 25)
person.greet()
```

**Output**:
```
Hi, I am Swati, and I am 25 years old.
```

#### **5.3 Why Use Constructors?**
1. Ensures all objects are initialized properly.
2. Simplifies the process of creating objects with attributes.

---

### **6. Practical Exercises**

#### **6.1 Create a Circle Class**
- Define a `Circle` class with:
  - Attribute: radius.
  - Methods: calculate area, calculate circumference.

```python
import math

class Circle:
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return math.pi * self.radius**2

    def circumference(self):
        return 2 * math.pi * self.radius

circle = Circle(5)
print(f"Area: {circle.area()}")
print(f"Circumference: {circle.circumference()}")
```

**Output**:
```
Area: 78.53981633974483
Circumference: 31.41592653589793
```

---

### **7. Wrap-Up: Review and Reflection**

#### **Reflection Questions**
1. What are the main advantages of using OOP?
2. Why is `self` important in methods?
3. What is the role of a constructor in a class?

#### **Recap Quiz**
1. Create a `Book` class with attributes `title`, `author`, and `price`. Add methods to display details and apply a discount.
2. How do you access an attribute of an object?
3. Write an example of a class with a default value for an attribute.

---------------------

<h1 align="center">Let's deep dive into above concept in more detailed manner</h1>

### **1. Introduction to Classes and Objects**

#### **1.1 What are Classes and Objects?**

1. **Class**:
   - A **class** is a blueprint or template for creating objects. It defines attributes (data) and methods (behavior) that the objects created from it will have.

2. **Object**:
   - An **object** is an instance of a class. It is a specific realization of the class blueprint.

3. **Analogy**:
   - **Class**: Think of a class as a cookie cutter.
   - **Object**: Each cookie created using the cutter is an object, sharing the same shape but with different ingredients or toppings.

#### **1.2 Why Use Classes and Objects?**
- They allow for **modularity**, **reuse**, and **organization** in code.
- Objects encapsulate data and functionality, making code cleaner and easier to maintain.

---

### **2. Creating and Using Classes**

#### **2.1 Defining a Class**
- A class is defined using the `class` keyword followed by the class name.

**Syntax**:
```python
class ClassName:
    # Class body
    pass
```

**Example**:
```python
class Person:
    pass
```

---

#### **2.2 Creating an Object**
- An object is created by calling the class like a function.

**Example**:
```python
person1 = Person()  # Create an object of the class Person
print(person1)      # Output: <__main__.Person object at 0x7f2b8d4a4f10>
```

---

#### **2.3 Adding Attributes and Methods**

1. **Attributes**:
   - Variables that store the state of an object.

2. **Methods**:
   - Functions defined within a class that operate on the attributes of the object.

**Example**:
```python
class Person:
    # Constructor to initialize attributes
    def __init__(self, name, age):
        self.name = name  # Instance attribute
        self.age = age    # Instance attribute

    # Method to display details
    def display(self):
        print(f"Name: {self.name}, Age: {self.age}")

# Creating an object
person1 = Person("Swati", 25)
person1.display()  # Output: Name: Swati, Age: 25
```

---

### **3. Types of Attributes**

#### **3.1 Instance Attributes**
- Defined inside the constructor (`__init__`).
- Unique to each object.

**Example**:
```python
person1 = Person("Swati", 25)
person2 = Person("Amit", 30)

print(person1.name)  # Output: Swati
print(person2.name)  # Output: Amit
```

---

#### **3.2 Class Attributes**
- Shared among all objects of the class.
- Defined directly inside the class but outside any methods.

**Example**:
```python
class Car:
    wheels = 4  # Class attribute

    def __init__(self, brand, model):
        self.brand = brand  # Instance attribute
        self.model = model  # Instance attribute

car1 = Car("Toyota", "Camry")
car2 = Car("Honda", "Civic")

print(car1.wheels)  # Output: 4
print(car2.wheels)  # Output: 4
```

---

### **4. Methods in Classes**

#### **4.1 Instance Methods**
- Operate on the object’s attributes.
- Require `self` as their first parameter.

**Example**:
```python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

rect = Rectangle(5, 3)
print(rect.area())  # Output: 15
```

---

#### **4.2 Class Methods**
- Operate on class attributes.
- Use `@classmethod` decorator and take `cls` as their first parameter.

**Example**:
```python
class Circle:
    pi = 3.14159  # Class attribute

    @classmethod
    def set_pi(cls, new_pi):
        cls.pi = new_pi

Circle.set_pi(3.14)
print(Circle.pi)  # Output: 3.14
```

---

#### **4.3 Static Methods**
- Don’t operate on instance or class attributes.
- Use `@staticmethod` decorator.

**Example**:
```python
class Calculator:
    @staticmethod
    def add(a, b):
        return a + b

print(Calculator.add(5, 3))  # Output: 8
```

---

### **5. Relationships Between Classes**

#### **5.1 Composition**
- A “has-a” relationship, where one class contains an instance of another class.

**Example**:
```python
class Engine:
    def start(self):
        print("Engine started")

class Car:
    def __init__(self, engine):
        self.engine = engine

    def start(self):
        self.engine.start()

engine = Engine()
car = Car(engine)
car.start()  # Output: Engine started
```

---

#### **5.2 Inheritance**
- A “is-a” relationship, where a child class inherits attributes and methods from a parent class.

**Example**:
```python
class Vehicle:
    def __init__(self, brand):
        self.brand = brand

    def start(self):
        print(f"{self.brand} vehicle started")

class Car(Vehicle):
    def __init__(self, brand, model):
        super().__init__(brand)
        self.model = model

car = Car("Toyota", "Camry")
car.start()  # Output: Toyota vehicle started
```

---

### **6. Practical Exercises**

#### **6.1 Define a BankAccount Class**
- Attributes: `account_number`, `balance`.
- Methods:
  1. `deposit(amount)`
  2. `withdraw(amount)`
  3. `display_balance()`

**Solution**:
```python
class BankAccount:
    def __init__(self, account_number, balance=0):
        self.account_number = account_number
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        print(f"Deposited: {amount}")

    def withdraw(self, amount):
        if amount > self.balance:
            print("Insufficient funds!")
        else:
            self.balance -= amount
            print(f"Withdrawn: {amount}")

    def display_balance(self):
        print(f"Balance: {self.balance}")

account = BankAccount(12345, 500)
account.deposit(200)
account.withdraw(100)
account.display_balance()
```

---

#### **6.2 Define a Library Class**
- Attributes: `books` (list).
- Methods:
  1. `add_book(title)`
  2. `remove_book(title)`
  3. `display_books()`

**Solution**:
```python
class Library:
    def __init__(self):
        self.books = []

    def add_book(self, title):
        self.books.append(title)
        print(f"Added book: {title}")

    def remove_book(self, title):
        if title in self.books:
            self.books.remove(title)
            print(f"Removed book: {title}")
        else:
            print(f"{title} not found!")

    def display_books(self):
        print("Books in library:")
        for book in self.books:
            print(f"- {book}")

library = Library()
library.add_book("Python 101")
library.add_book("Data Science")
library.display_books()
library.remove_book("Python 101")
library.display_books()
```

---

### **7. Wrap-Up: Review and Reflection**

#### **Reflection Questions**
1. What are the key differences between instance and class attributes?
2. When would you use a static method instead of an instance method?
3. How does inheritance simplify code?

#### **Recap Quiz**
1. Create a `Student` class with attributes `name`, `roll_number`, and `marks`. Add methods to:
   - Display details.
   - Update marks.
2. Write an example of composition in a class.
3. What is the purpose of `super()` in inheritance?

-------------

# **Constructors in Python**

---

### **1. What is a Constructor?**
- A **constructor** is a special method in a class that initializes the attributes of an object.
- It is automatically invoked when an object of the class is created.
- Constructors are defined using the `__init__` method in Python.

---

### **2. Purpose of a Constructor**
- **Initialization**: Automatically initializes attributes when an object is created.
- **Dynamic Assignment**: Allows passing arguments to initialize attributes with different values for each object.
- **Code Simplification**: Reduces the need to manually set attributes for each object after creation.

---

### **3. Constructor Syntax**

```python
class ClassName:
    def __init__(self, parameters):
        # Initialize attributes
        self.attribute = value
```

**Example**:
```python
class Person:
    def __init__(self, name, age):
        self.name = name  # Assign name to the object
        self.age = age    # Assign age to the object

person = Person("Swati", 25)
print(person.name)  # Output: Swati
print(person.age)   # Output: 25
```

---

### **4. Types of Constructors**

Python supports three types of constructors:

#### **4.1 Default Constructor**
- A constructor with no parameters (other than `self`).
- Initializes attributes with fixed or default values.

**Example**:
```python
class Car:
    def __init__(self):  # No parameters
        self.brand = "Toyota"
        self.model = "Camry"

car = Car()
print(car.brand)  # Output: Toyota
print(car.model)  # Output: Camry
```

---

#### **4.2 Parameterized Constructor**
- A constructor that accepts parameters to initialize attributes dynamically.
- Allows flexibility and customization when creating objects.

**Example**:
```python
class Car:
    def __init__(self, brand, model):  # Parameters for dynamic initialization
        self.brand = brand
        self.model = model

car1 = Car("Toyota", "Camry")
car2 = Car("Honda", "Civic")

print(car1.brand)  # Output: Toyota
print(car2.model)  # Output: Civic
```

---

#### **4.3 Constructor with Default Parameters**
- A constructor with default values for some or all parameters. If values are not provided during object creation, the defaults are used.

**Example**:
```python
class Laptop:
    def __init__(self, brand="Dell", processor="i5"):
        self.brand = brand
        self.processor = processor

laptop1 = Laptop()  # Uses default values
laptop2 = Laptop("HP", "i7")  # Overrides default values

print(laptop1.brand)  # Output: Dell
print(laptop2.processor)  # Output: i7
```

---

### **5. Advanced Constructor Concepts**

#### **5.1 Constructor Overloading**
- Python doesn’t support constructor overloading natively (as in Java or C++). 
- You can achieve similar behavior using default arguments or `*args` and `**kwargs`.

**Example with Default Arguments**:
```python
class Person:
    def __init__(self, name="Unknown", age=0):
        self.name = name
        self.age = age

person1 = Person("Swati", 25)
person2 = Person()  # Defaults used

print(person1.name)  # Output: Swati
print(person2.age)   # Output: 0
```

**Example with `*args`**:
```python
class Person:
    def __init__(self, *args):
        if len(args) == 2:
            self.name, self.age = args
        else:
            self.name, self.age = "Unknown", 0

person1 = Person("Swati", 25)
person2 = Person()

print(person1.name)  # Output: Swati
print(person2.age)   # Output: 0
```

---

#### **5.2 Calling Another Method Inside a Constructor**
- A constructor can call other methods in the class for additional processing.

**Example**:
```python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width
        self.area = self.calculate_area()  # Call another method

    def calculate_area(self):
        return self.length * self.width

rect = Rectangle(5, 3)
print(rect.area)  # Output: 15
```

---

#### **5.3 Using `super()` in a Constructor**
- In classes with **inheritance**, the `super()` function is used to call the parent class constructor.

**Example**:
```python
class Vehicle:
    def __init__(self, brand):
        self.brand = brand

class Car(Vehicle):
    def __init__(self, brand, model):
        super().__init__(brand)  # Call parent constructor
        self.model = model

car = Car("Toyota", "Camry")
print(car.brand)  # Output: Toyota
print(car.model)  # Output: Camry
```

---

#### **5.4 Using `__new__()` with `__init__()`**
- The `__new__()` method is called before `__init__()` and is responsible for creating the object.
- Rarely used unless working with metaclasses or singleton patterns.

**Example**:
```python
class Singleton:
    _instance = None

    def __new__(cls, *args, **kwargs):
        if not cls._instance:
            cls._instance = super().__new__(cls, *args, **kwargs)
        return cls._instance

    def __init__(self, name):
        self.name = name

obj1 = Singleton("First")
obj2 = Singleton("Second")

print(obj1.name)  # Output: Second
print(obj1 is obj2)  # Output: True (Same instance)
```

---

### **6. Practical Exercises**

#### **6.1 Define a Library Class**
- Create a `Library` class with:
  - Attributes: `library_name` (default: "Public Library"), `books` (list of books).
  - Method to display all books.

**Solution**:
```python
class Library:
    def __init__(self, library_name="Public Library", books=None):
        self.library_name = library_name
        self.books = books if books else []

    def display_books(self):
        print(f"Books in {self.library_name}:")
        for book in self.books:
            print(f"- {book}")

library = Library(books=["Python 101", "Data Science Handbook"])
library.display_books()
```

**Output**:
```
Books in Public Library:
- Python 101
- Data Science Handbook
```

---

#### **6.2 Implement a Product Class**
- Create a `Product` class with:
  - Attributes: `name`, `price`, `discount` (default: 0).
  - Method to calculate the discounted price.

**Solution**:
```python
class Product:
    def __init__(self, name, price, discount=0):
        self.name = name
        self.price = price
        self.discount = discount

    def discounted_price(self):
        return self.price - (self.price * self.discount / 100)

product = Product("Laptop", 1000, 10)
print(f"Discounted Price: ${product.discounted_price():.2f}")
```

**Output**:
```
Discounted Price: $900.00
```

---

### **7. Common Mistakes with Constructors**

1. **Missing `self`**:
   - Forgetting to use `self` when defining attributes inside the constructor leads to `AttributeError`.

2. **Calling Constructor Manually**:
   - Directly calling `__init__()` without using the class properly can result in unexpected behavior.

3. **Mutability of Default Arguments**:
   - Using mutable objects (e.g., lists, dictionaries) as default arguments can lead to shared state across instances.

---

### **8. Wrap-Up: Review and Reflection**

By the end of today, You should:
- Be confident in using default, parameterized, and advanced constructors.
- Understand how to initialize objects dynamically.
- Know how to work with `super()` and `__new__()` for advanced use cases.

---

#### **Reflection Questions**
1. Why is the `__init__()` method called a constructor?
2. How can you create a constructor with default parameters?
3. What is the difference between `__init__()` and `__new__()`?

#### **Recap Quiz**
1. Create a class `Employee` with attributes `name`, `salary`, and `position` (default: "Intern").
2. How do you handle optional arguments in a constructor?
3. Write a constructor that initializes a list of tasks for a `Project` class.


----------------

<p align="center"> <a href="./Day16.md" target=""><img align="center" src="./../Resources/back.png" width="100" /></a>  <a href="./Day18.md" target=""><img align="center" src="./../Resources/next.png" width="100" /></a> </p>

---------------
