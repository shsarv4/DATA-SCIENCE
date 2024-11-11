## **Day 3: Strings and String Manipulation**

### **Objective**
By the end of Day 3, Swati, you will understand strings, know how to manipulate them, and be familiar with important string functions in Python. We’ll cover string operations, slicing, and formatting, with hands-on examples.

#### Video Links

1. [https://www.youtube.com/watch?v=ORCuz7s5cCY&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=11](https://www.youtube.com/watch?v=ORCuz7s5cCY&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=11)
2. [https://www.youtube.com/watch?v=Pu5bqySSSS0&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=12](https://www.youtube.com/watch?v=Pu5bqySSSS0&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=12)
3. [https://www.youtube.com/watch?v=WvG-R-xXouA&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=13](https://www.youtube.com/watch?v=WvG-R-xXouA&list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg&index=13)
---

### **1. Theory**

#### **1.1 Introduction to Strings**

- **What is a String?**
  - A string is a sequence of characters enclosed within single (`'...'`), double (`"..."`), or triple quotes (`'''...'''` or `"""..."""`). Strings are commonly used for representing text data.
  - **Examples**:
    ```python
    name = "Swati"
    quote = 'The journey of learning is never-ending.'
    description = """This is a multi-line
    string in Python."""
    ```

- **String Immutability**:
  - Strings in Python are immutable, meaning once a string is created, it cannot be modified. However, you can create a new string based on modifications of the original one.

#### **1.2 Basic String Operations**

- **Concatenation**: Combine strings using the `+` operator.
  ```python
  first_name = "Swati"
  last_name = "Sahu"
  full_name = first_name + " " + last_name
  print(full_name)  # Output: Swati Sahu
  ```

- **Repetition**: Repeat strings using the `*` operator.
  ```python
  laugh = "Ha" * 3
  print(laugh)  # Output: HaHaHa
  ```

- **Length of a String**: Use `len()` to find the length of a string.
  ```python
  text = "Hello, Swati!"
  print(len(text))  # Output: 13
  ```

#### **1.3 Indexing and Slicing Strings**

- **Indexing**:
  - Each character in a string has a position called an index. Python uses zero-based indexing, so the first character is at index `0`.
  - **Example**:
    ```python
    greeting = "Hello, Swati!"
    print(greeting[0])  # Output: H
    print(greeting[7])  # Output: S
    ```

- **Negative Indexing**:
  - You can use negative indices to access characters from the end of the string.
  - **Example**:
    ```python
    print(greeting[-1])  # Output: !
    print(greeting[-6])  # Output: S
    ```

- **Slicing**:
  - Use slicing to extract a substring from a string. The syntax is `string[start:end]`, where `start` is inclusive, and `end` is exclusive.
  - **Example**:
    ```python
    phrase = "Python Programming"
    print(phrase[0:6])    # Output: Python
    print(phrase[7:])     # Output: Programming
    print(phrase[:6])     # Output: Python
    ```

#### **1.4 Important String Methods**

1. **`.upper()`** and **`.lower()`**: Convert to uppercase or lowercase.
   ```python
   text = "Learning Python"
   print(text.upper())    # Output: LEARNING PYTHON
   print(text.lower())    # Output: learning python
   ```

2. **`.strip()`**: Remove leading and trailing whitespace.
   ```python
   messy_text = "   Hello, Swati!   "
   print(messy_text.strip())  # Output: Hello, Swati!
   ```

3. **`.replace(old, new)`**: Replace parts of a string.
   ```python
   text = "I love painting."
   updated_text = text.replace("painting", "coding")
   print(updated_text)  # Output: I love coding.
   ```

4. **`.find(substring)`**: Find the position of a substring.
   ```python
   quote = "To be or not to be."
   print(quote.find("be"))   # Output: 3 (first occurrence)
   ```

5. **`.split(delimiter)`**: Split a string into a list based on a delimiter.
   ```python
   sentence = "Python is fun to learn"
   words = sentence.split(" ")
   print(words)  # Output: ['Python', 'is', 'fun', 'to', 'learn']
   ```

6. **`.join(iterable)`**: Join elements of an iterable (like a list) into a single string.
   ```python
   words = ['Learning', 'Python', 'is', 'fun']
   sentence = " ".join(words)
   print(sentence)  # Output: Learning Python is fun
   ```

#### **1.5 String Formatting**

1. **Using f-Strings**:
   - F-strings make it easy to format strings by embedding variables directly in the text.
   ```python
   name = "Swati"
   age = 25
   intro = f"My name is {name} and I am {age} years old."
   print(intro)
   ```

2. **Using `.format()`**:
   ```python
   language = "Python"
   sentence = "I love programming in {}.".format(language)
   print(sentence)  # Output: I love programming in Python.
   ```

---

### **2. Practical Examples**

Let’s look at some practical applications of strings that Swati might enjoy working with.

#### **2.1 Personal Introduction**

```python
name = "Swati"
hobby = "painting"
city = "Bhopal"

intro = f"Hello, I'm {name}, and I enjoy {hobby} in my free time. I'm from {city}."
print(intro)
```

#### **2.2 Creating a Simple Poem**

```python
line1 = "Roses are red,"
line2 = "Violets are blue,"
line3 = "Python is great,"
line4 = "And so are you!"

poem = line1 + "\n" + line2 + "\n" + line3 + "\n" + line4
print(poem)
```

#### **2.3 Replacing Text in a Quote**

```python
quote = "Learning Python is challenging."
updated_quote = quote.replace("challenging", "fun")
print(updated_quote)  # Output: Learning Python is fun.
```

#### **2.4 Joining a List of Words**

```python
words = ["Swati", "loves", "learning", "Python"]
sentence = " ".join(words)
print(sentence)  # Output: Swati loves learning Python
```

#### **2.5 Fun with Slicing**

```python
phrase = "Hello, Swati! Welcome to Python."
print(phrase[:5])      # Output: Hello
print(phrase[7:12])    # Output: Swati
print(phrase[-6:])     # Output: Python
```

---

### **3. Hands-On Practice Exercises**

1. **Exercise: Personal Bio**
   - Create variables for your name, favorite activity, and favorite food. Use `f-string` formatting to create a sentence with this information.
   - Example:
     ```python
     name = "Swati"
     activity = "painting"
     food = "pasta"
     bio = f"Hi, I'm {name}. I enjoy {activity} and my favorite food is {food}."
     print(bio)
     ```

2. **Exercise: Motivational Quote**
   - Choose a motivational quote and store it in a variable. Use `.upper()` and `.lower()` methods to display the quote in uppercase and lowercase.
   - Example:
     ```python
     quote = "Believe in yourself and all that you are."
     print(quote.upper())
     print(quote.lower())
     ```

3. **Exercise: Slicing Practice**
   - Define a string with at least 10 characters. Extract and print:
     - The first 5 characters
     - The last 3 characters
     - A substring from the 3rd to 8th character
   - Example:
     ```python
     text = "PythonProgramming"
     print(text[:5])      # Output: Pytho
     print(text[-3:])     # Output: ing
     print(text[2:8])     # Output: thonPr
     ```

4. **Exercise: Find and Replace**
   - Write a short sentence. Use `.find()` to locate a word and `.replace()` to change that word.
   - Example:
     ```python
     sentence = "Learning Python is enjoyable."
     position = sentence.find("enjoyable")
     print("Position of 'enjoyable':", position)
     updated_sentence = sentence.replace("enjoyable", "amazing")
     print(updated_sentence)
     ```

5. **Exercise: Split and Join**
   - Create a string of words separated by commas. Split the string into individual words, then join them with spaces.
   - Example:
     ```python
     items = "apple,banana,orange,grape"
     fruits = items.split(",")
     sentence = " and ".join(fruits)
     print(sentence)  # Output: apple and banana and orange and grape
     ```

---

### **4. Challenge Problems**

1. **Reverse a String**

:
   - Write code that takes a string and prints it in reverse.
   - **Hint**: Use slicing with a step of `-1`.
   ```python
   text = "Swati loves Python"
   print(text[::-1])
   ```

2. **Create a Username**:
   - Take your full name as input, split it into first and last names, then generate a username using the first three letters of each.
   - **Hint**: Use `.split()` and slicing.
   ```python
   full_name = "Swati Sahu"
   name_parts = full_name.split()
   username = name_parts[0][:3] + name_parts[1][:3]
   print(username)  # Output: SwaSah
   ```

3. **Palindrome Checker**:
   - Write a program that checks if a given word is a palindrome (reads the same forward and backward).
   - **Hint**: Use slicing to reverse the string and compare.
   ```python
   word = "madam"
   is_palindrome = word == word[::-1]
   print(f"{word} is a palindrome:", is_palindrome)
   ```

---

### **5. Wrap-Up: Review and Reflection**

By the end of today, Swati, you should be comfortable with using strings, performing different types of operations, and working with string methods.

#### **Reflection Questions**
1. How can you use string slicing to select specific parts of text?
2. Which string method do you find the most useful, and why?
3. How does immutability impact how you work with strings?

#### **Recap Quiz**
1. What does the `replace()` method do?
2. How would you find the length of a string in Python?
3. Write an example where you join a list of words with a custom separator.

---

This detailed breakdown ensures that Swati gets hands-on experience with essential string operations, along with exercises and challenges that bring real learning. Let me know if you’re ready for **Day 4**!
#### [Prev](./PYTHON/Day03.md) ___ [Next](./PYTHON/Day05.md)
