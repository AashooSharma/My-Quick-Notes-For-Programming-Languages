Perfect 👍 Ab Part 4B (Advanced Problems with Solutions) start karte hain jisme recursion, file handling, OOP aur thoda advanced Python coding problems honge. Ye continuation hai Part-4 ka:

---

# 📘 Python Syntax & Practice – Part 4B (Advanced Problems)

## 🔹 Section 6: Recursion Problems

### 26. Factorial using Recursion

```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)

print(factorial(5))
```

**Output:**

```
120
```

**Explanation:**
Recursion repeatedly multiplies `n * factorial(n-1)` until `n == 0`.

---

### 27. Fibonacci using Recursion

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

print([fibonacci(i) for i in range(7)])
```

**Output:**

```
[0, 1, 1, 2, 3, 5, 8]
```

---

### 28. Sum of Digits using Recursion

```python
def sum_digits(n):
    if n == 0:
        return 0
    return n % 10 + sum_digits(n // 10)

print(sum_digits(1234))
```

**Output:**

```
10
```

---

### 29. Reverse String using Recursion

```python
def reverse_string(s):
    if len(s) == 0:
        return ""
    return reverse_string(s[1:]) + s[0]

print(reverse_string("hello"))
```

**Output:**

```
olleh
```

---

## 🔹 Section 7: File Handling Problems

### 30. Write & Read a File

```python
with open("sample.txt", "w") as f:
    f.write("Hello Python File Handling")

with open("sample.txt", "r") as f:
    print(f.read())
```

**Output:**

```
Hello Python File Handling
```

---

### 31. Count Words in a File

```python
with open("sample.txt", "r") as f:
    data = f.read()
    print("Words:", len(data.split()))
```

---

### 32. Copy File Content

```python
with open("sample.txt", "r") as src:
    with open("copy.txt", "w") as dest:
        dest.write(src.read())
```

---

### 33. Count Lines in File

```python
with open("sample.txt", "r") as f:
    lines = f.readlines()
    print("Line count:", len(lines))
```

---

## 🔹 Section 8: Object-Oriented Problems

### 34. Class & Object

```python
class Student:
    def __init__(self, name, roll):
        self.name = name
        self.roll = roll

    def show(self):
        print(f"Name: {self.name}, Roll: {self.roll}")

s1 = Student("Aashoo", 101)
s1.show()
```

**Output:**

```
Name: Aashoo, Roll: 101
```

---

### 35. Inheritance Example

```python
class Animal:
    def speak(self):
        print("Animal makes a sound")

class Dog(Animal):
    def speak(self):
        print("Dog barks")

d = Dog()
d.speak()
```

**Output:**

```
Dog barks
```

---

### 36. Encapsulation

```python
class Bank:
    def __init__(self):
        self.__balance = 1000   # private variable

    def deposit(self, amt):
        self.__balance += amt

    def get_balance(self):
        return self.__balance

b = Bank()
b.deposit(500)
print(b.get_balance())
```

**Output:**

```
1500
```

---

### 37. Polymorphism

```python
class Bird:
    def fly(self):
        print("Some birds fly")

class Sparrow(Bird):
    def fly(self):
        print("Sparrow flies high")

class Ostrich(Bird):
    def fly(self):
        print("Ostrich cannot fly")

for bird in [Sparrow(), Ostrich()]:
    bird.fly()
```

**Output:**

```
Sparrow flies high
Ostrich cannot fly
```

---

## 🔹 Section 9: Advanced Coding Challenges

### 38. Palindrome Check

```python
def is_palindrome(s):
    return s == s[::-1]

print(is_palindrome("madam"))
print(is_palindrome("hello"))
```

**Output:**

```
True
False
```

---

### 39. Armstrong Number

```python
def is_armstrong(n):
    digits = str(n)
    power = len(digits)
    return n == sum(int(d)**power for d in digits)

print(is_armstrong(153))
print(is_armstrong(123))
```

**Output:**

```
True
False
```

---

### 40. Anagram Check

```python
def is_anagram(s1, s2):
    return sorted(s1) == sorted(s2)

print(is_anagram("listen", "silent"))
print(is_anagram("hello", "world"))
```

**Output:**

```
True
False
```

---

### 41. Prime Factors

```python
def prime_factors(n):
    factors = []
    i = 2
    while i <= n:
        if n % i == 0:
            factors.append(i)
            n //= i
        else:
            i += 1
    return factors

print(prime_factors(56))
```

**Output:**

```
[2, 2, 2, 7]
```

---

### 42. Find Missing Number in List

```python
def find_missing(arr, n):
    total = n*(n+1)//2
    return total - sum(arr)

print(find_missing([1,2,4,5,6], 6))
```

**Output:**

```
3
```

---

### 43. Remove Duplicates from List

```python
arr = [1,2,2,3,4,4,5]
unique = list(set(arr))
print(unique)
```

**Output:**

```
[1, 2, 3, 4, 5]
```

---

### 44. Longest Word in a Sentence

```python
def longest_word(sentence):
    words = sentence.split()
    return max(words, key=len)

print(longest_word("Python is amazing language"))
```

**Output:**

```
language
```

---

### 45. Binary Search

```python
def binary_search(arr, target):
    low, high = 0, len(arr)-1
    while low <= high:
        mid = (low+high)//2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid+1
        else:
            high = mid-1
    return -1

print(binary_search([1,2,3,4,5,6], 4))
```

**Output:**

```
3
```

---

📌 Yaha tak total **45 problems** ho gaye (Basic + Intermediate + Advanced).
Agla **Part 4C** me main aur **5+ extra advanced problems (Graphs, Sorting, OOP projects, Decorators, Generators)** add karunga.

---

👉 Kya aap chahte ho ki main Part 4C me **DSA level problems (Sorting, Searching, Graph, DP)** bhi add karu ya sirf **Python-focused real-world problems** rakhu?
