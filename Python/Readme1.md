# 🐍 Python Syntax & Examples Cheat Sheet

This README is a **complete Python syntax revision guide** with examples, explanations, and outputs. Perfect for quickly refreshing your memory.

---

## 1. Basics

### Print Statement

```python
print("Hello, Python!")
```

**Output:**

```
Hello, Python!
```

### Comments

```python
# Single line comment
'''
This is a
multi-line comment
'''
```

### Variables & Types

```python
x = 10          # int
y = 3.14        # float
name = "Aashoo" # string
flag = True     # boolean
```

Check type:

```python
print(type(name))
```

**Output:** `<class 'str'>`

### Type Casting

```python
num = int("10")
flt = float("3.5")
```

---

## 2. Operators

```python
a, b = 5, 2
print(a + b)   # Addition → 7
print(a - b)   # Subtraction → 3
print(a * b)   # Multiplication → 10
print(a / b)   # Division → 2.5
print(a // b)  # Floor Division → 2
print(a % b)   # Modulus → 1
print(a ** b)  # Power → 25
```

---

## 3. Strings

```python
text = "Python"
print(text[0])      # P
print(text[-1])     # n
print(text[0:3])    # Pyt
print(text[::-1])   # nohtyP

print(text.upper()) # PYTHON
print(text.lower()) # python
print(text.replace("Py", "My")) # Mython
```

f-String Formatting:

```python
name = "Aashoo"
age = 24
print(f"My name is {name} and I am {age} years old.")
```

**Output:** `My name is Aashoo and I am 24 years old.`

---

## 4. Conditionals

```python
x = 10
if x > 5:
    print("Greater than 5")
elif x == 5:
    print("Equal to 5")
else:
    print("Smaller than 5")
```

Ternary Operator:

```python
age = 18
status = "Adult" if age >= 18 else "Minor"
print(status)
```

---

## 5. Loops

### For Loop

```python
for i in range(5):
    print(i)
```

**Output:** `0 1 2 3 4`

### While Loop

```python
count = 3
while count > 0:
    print(count)
    count -= 1
```

**Output:** `3 2 1`

### Loop with Else

```python
for i in range(3):
    print(i)
else:
    print("Loop finished!")
```

---

## 6. Data Structures

### List

```python
fruits = ["apple", "banana", "cherry"]
fruits.append("mango")
print(fruits)
```

**Output:** `["apple", "banana", "cherry", "mango"]`

### Tuple

```python
tuple1 = (1, 2, 3)
print(tuple1[1])
```

### Set

```python
s = {1, 2, 3}
s.add(4)
print(s)
```

### Dictionary

```python
person = {"name": "Aashoo", "age": 24}
print(person["name"])
```

**Output:** `Aashoo`

---

## 7. Functions

```python
def greet(name):
    return f"Hello {name}"

print(greet("Python"))
```

**Output:** `Hello Python`

Lambda Function:

```python
square = lambda x: x * x
print(square(4))
```

**Output:** `16`

---

## 8. Classes & Objects

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        print("Hello, " + self.name)

p = Person("Aashoo")
p.greet()
```

**Output:** `Hello, Aashoo`

---

## 9. File Handling

```python
with open("demo.txt", "w") as f:
    f.write("Hello File")

with open("demo.txt", "r") as f:
    print(f.read())
```

---

## 10. Exception Handling

```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Can't divide by zero!")
finally:
    print("Done")
```

**Output:**

```
Can't divide by zero!
Done
```

---

## 11. Modules & Imports

```python
import math
print(math.sqrt(16))
```

**Output:** `4.0`

```python
from datetime import datetime
print(datetime.now())
```

---

## 12. Comprehensions

```python
squares = [x*x for x in range(5)]
print(squares)
```

**Output:** `[0, 1, 4, 9, 16]`

Dictionary comprehension:

```python
nums = {x: x*x for x in range(3)}
print(nums)
```

**Output:** `{0:0, 1:1, 2:4}`

---

## 13. Useful Built-in Functions

```python
print(len([1,2,3]))     # 3
print(max(4, 7, 2))     # 7
print(min(4, 7, 2))     # 2
print(sum([1,2,3]))     # 6
print(sorted([3,1,2]))  # [1,2,3]
```

---

## 14. Advanced

### Generator

```python
def my_gen():
    yield 1
    yield 2
    yield 3

for x in my_gen():
    print(x)
```

### Decorator

```python
def decorator(func):
    def wrapper():
        print("Before function")
        func()
        print("After function")
    return wrapper

@decorator
def say_hello():
    print("Hello!")

say_hello()
```

**Output:**

```
Before function
Hello!
After function
```

---

# ✅ Summary

* Python syntax is simple but powerful.
* Focus on loops, functions, OOP, and libraries.
* Practice small examples to remember syntax.
* This sheet works as a quick reference + revision guide.
