Perfect 👍 Ab main aapko **Python Practice Problems – Part 4** deta hu, jisme **50+ coding questions with answers (code + output + explanation)** diye gaye hain.
Ye aapke liye ek **ready-made question bank** hoga jo placement aur revision dono ke liye useful rahega.

---

# 📘 Python Practice Problems – Part 4

---

## 🟢 Section 1: Basic Problems (Beginner Level)

### Q1. Sum of Two Numbers

```python
a = 10
b = 20
sum = a + b
print("Sum:", sum)
```

**Output:**

```
Sum: 30
```

**Explanation:** Simply `+` operator use karke do numbers ka sum kiya.

---

### Q2. Swap Two Variables

```python
a, b = 5, 10
a, b = b, a
print("a =", a, "b =", b)
```

**Output:**

```
a = 10 b = 5
```

**Explanation:** Python tuple unpacking se swap directly possible hai.

---

### Q3. Check Even or Odd

```python
num = 7
if num % 2 == 0:
    print("Even")
else:
    print("Odd")
```

**Output:**

```
Odd
```

**Explanation:** `% 2 == 0` → even, otherwise odd.

---

### Q4. Largest of Three Numbers

```python
a, b, c = 12, 5, 30
print("Largest:", max(a, b, c))
```

**Output:**

```
Largest: 30
```

---

### Q5. Simple Calculator

```python
a, b = 15, 3
print("Add:", a+b)
print("Subtract:", a-b)
print("Multiply:", a*b)
print("Divide:", a/b)
```

**Output:**

```
Add: 18
Subtract: 12
Multiply: 45
Divide: 5.0
```

---

## 🟡 Section 2: Loops & Patterns

### Q6. Print First 10 Natural Numbers

```python
for i in range(1, 11):
    print(i, end=" ")
```

**Output:**

```
1 2 3 4 5 6 7 8 9 10
```

---

### Q7. Print Star Triangle

```python
rows = 5
for i in range(1, rows+1):
    print("*" * i)
```

**Output:**

```
*
**
***
****
*****
```

---

### Q8. Print Rectangle of Stars

```python
rows, cols = 4, 5
for i in range(rows):
    print("* " * cols)
```

**Output:**

```
* * * * * 
* * * * * 
* * * * * 
* * * * * 
```

---

### Q9. Pyramid Pattern

```python
rows = 5
for i in range(1, rows+1):
    print(" "*(rows-i) + "*"*(2*i-1))
```

**Output:**

```
    *
   ***
  *****
 *******
*********
```

---

### Q10. Number Pattern

```python
rows = 5
for i in range(1, rows+1):
    for j in range(1, i+1):
        print(j, end=" ")
    print()
```

**Output:**

```
1 
1 2 
1 2 3 
1 2 3 4 
1 2 3 4 5 
```

---

## 🔵 Section 3: Math Problems

### Q11. Factorial of a Number

```python
num = 5
fact = 1
for i in range(1, num+1):
    fact *= i
print("Factorial:", fact)
```

**Output:**

```
Factorial: 120
```

---

### Q12. Fibonacci Series

```python
n = 7
a, b = 0, 1
for i in range(n):
    print(a, end=" ")
    a, b = b, a+b
```

**Output:**

```
0 1 1 2 3 5 8
```

---

### Q13. Prime Number Check

```python
num = 29
flag = True
for i in range(2, int(num**0.5)+1):
    if num % i == 0:
        flag = False
        break
print("Prime" if flag else "Not Prime")
```

**Output:**

```
Prime
```

---

### Q14. Armstrong Number

```python
num = 153
s = sum(int(digit)**3 for digit in str(num))
print("Armstrong" if s == num else "Not Armstrong")
```

**Output:**

```
Armstrong
```

---

### Q15. Palindrome Number

```python
num = 121
if str(num) == str(num)[::-1]:
    print("Palindrome")
else:
    print("Not Palindrome")
```

**Output:**

```
Palindrome
```

---

## 🟠 Section 4: String Problems

### Q16. Reverse a String

```python
s = "hello"
print(s[::-1])
```

**Output:**

```
olleh
```

---

### Q17. Count Vowels and Consonants

```python
s = "python"
vowels = "aeiou"
v, c = 0, 0
for ch in s:
    if ch in vowels:
        v += 1
    else:
        c += 1
print("Vowels:", v, "Consonants:", c)
```

**Output:**

```
Vowels: 1 Consonants: 5
```

---

### Q18. Check Anagram

```python
s1, s2 = "listen", "silent"
print("Anagram" if sorted(s1) == sorted(s2) else "Not Anagram")
```

**Output:**

```
Anagram
```

---

### Q19. Remove Duplicates

```python
s = "programming"
print("".join(sorted(set(s), key=s.index)))
```

**Output:**

```
progamin
```

---

### Q20. Word Frequency Counter

```python
text = "apple banana apple orange banana apple"
words = text.split()
freq = {}
for w in words:
    freq[w] = freq.get(w, 0) + 1
print(freq)
```

**Output:**

```
{'apple': 3, 'banana': 2, 'orange': 1}
```

---

## 🔴 Section 5: List/Array Problems

### Q21. Reverse a List

```python
arr = [1, 2, 3, 4]
print(arr[::-1])
```

**Output:**

```
[4, 3, 2, 1]
```

---

### Q22. Find Max and Min in List

```python
arr = [10, 25, 3, 78, 45]
print("Max:", max(arr), "Min:", min(arr))
```

**Output:**

```
Max: 78 Min: 3
```

---

### Q23. Linear Search

```python
arr = [10, 20, 30, 40]
x = 30
print("Found" if x in arr else "Not Found")
```

**Output:**

```
Found
```

---

### Q24. Binary Search

```python
arr = [10, 20, 30, 40, 50]
x = 30
low, high = 0, len(arr)-1
while low <= high:
    mid = (low+high)//2
    if arr[mid] == x:
        print("Found at index", mid)
        break
    elif arr[mid] < x:
        low = mid+1
    else:
        high = mid-1
```

**Output:**

```
Found at index 2
```

---

### Q25. Bubble Sort

```python
arr = [64, 25, 12, 22, 11]
n = len(arr)
for i in range(n):
    for j in range(0, n-i-1):
        if arr[j] > arr[j+1]:
            arr[j], arr[j+1] = arr[j+1], arr[j]
print(arr)
```

**Output:**

```
[11, 12, 22, 25, 64]
```

---

⚡ Ye part-4 abhi tak **25 problems cover karta hai** (Basic + Patterns + Math + Strings + Lists).
Next update me main **remaining 25+ problems** add karunga jisme **recursion, file handling, OOP, advanced coding challenges** honge.

---

👉 Kya aap chahte ho ki main **ek hi file (README style)** me ye **50+ problems complete** bana kar do, ya phir ise **Part 4A (Easy + Medium)** aur **Part 4B (Advanced)** me tod kar bheju?
