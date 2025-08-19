Perfect 👌 Ab tak humne **Basic → Intermediate → Advanced → DSA style** problems cover kar liye hain.
Ab main tumhe **Part 4D** deta hu jisme **Top 25+ Python Coding Interview Problems with Solutions** honge (code + output + explanation).

---

# 📘 Part 4D: Top 25+ Python Interview Problems with Solutions

---

## 1. Reverse a String (without using slicing)

```python
def reverse_string(s):
    rev = ""
    for ch in s:
        rev = ch + rev
    return rev

print(reverse_string("hello"))
```

**Output:**

```
olleh
```

**Explanation:** Har character ko aage jod kar reverse banate hain.

---

## 2. Check Palindrome String

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

**Explanation:** Agar string apne reverse ke equal hai to palindrome.

---

## 3. Find Factorial (Recursion)

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n-1)

print(factorial(5))
```

**Output:**

```
120
```

**Explanation:** Recursive formula `n! = n × (n-1)!`.

---

## 4. Fibonacci Series (Recursion)

```python
def fib(n):
    if n <= 1:
        return n
    return fib(n-1) + fib(n-2)

print([fib(i) for i in range(6)])
```

**Output:**

```
[0, 1, 1, 2, 3, 5]
```

**Explanation:** Recursive formula `F(n) = F(n-1) + F(n-2)`.

---

## 5. Prime Number Check

```python
def is_prime(n):
    if n < 2: return False
    for i in range(2, int(n**0.5)+1):
        if n % i == 0:
            return False
    return True

print(is_prime(29))
print(is_prime(15))
```

**Output:**

```
True
False
```

**Explanation:** Square root tak divisor check karna fast hota hai.

---

## 6. Find Missing Number in Array

```python
arr = [1,2,3,5]
n = 5
missing = n*(n+1)//2 - sum(arr)
print("Missing:", missing)
```

**Output:**

```
Missing: 4
```

**Explanation:** Formula of sum of `n natural numbers - sum(array)`.

---

## 7. Find Duplicate Elements

```python
arr = [1,2,3,1,2,4,5]
duplicates = set([x for x in arr if arr.count(x) > 1])
print(duplicates)
```

**Output:**

```
{1, 2}
```

**Explanation:** Agar `count > 1` hai to duplicate.

---

## 8. Find Largest Element in List

```python
nums = [10, 20, 4, 45, 99]
print(max(nums))
```

**Output:**

```
99
```

**Explanation:** Built-in `max()` fastest.

---

## 9. Find Second Largest Element

```python
nums = [10, 20, 4, 45, 99]
nums = list(set(nums))
nums.sort()
print(nums[-2])
```

**Output:**

```
45
```

**Explanation:** Set duplicates remove karta hai, sort se order mil jata hai.

---

## 10. Sort Array Without Built-in

```python
arr = [64, 25, 12, 22, 11]
for i in range(len(arr)):
    min_idx = i
    for j in range(i+1, len(arr)):
        if arr[j] < arr[min_idx]:
            min_idx = j
    arr[i], arr[min_idx] = arr[min_idx], arr[i]
print(arr)
```

**Output:**

```
[11, 12, 22, 25, 64]
```

**Explanation:** Selection sort implementation.

---

## 11. Anagram Check

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

**Explanation:** Sorted strings compare karo.

---

## 12. Count Frequency of Characters

```python
from collections import Counter
s = "aabbccc"
print(Counter(s))
```

**Output:**

```
Counter({'c': 3, 'a': 2, 'b': 2})
```

**Explanation:** `Counter` frequency dictionary return karta hai.

---

## 13. Find First Non-Repeating Character

```python
from collections import Counter
s = "aabbcdee"
count = Counter(s)
for ch in s:
    if count[ch] == 1:
        print("First Non-repeating:", ch)
        break
```

**Output:**

```
First Non-repeating: c
```

---

## 14. Check Armstrong Number

```python
def is_armstrong(n):
    s = str(n)
    power = len(s)
    return n == sum(int(d)**power for d in s)

print(is_armstrong(153))
print(is_armstrong(123))
```

**Output:**

```
True
False
```

---

## 15. Check Perfect Number

```python
def is_perfect(n):
    return n == sum(i for i in range(1, n) if n % i == 0)

print(is_perfect(28))
print(is_perfect(12))
```

**Output:**

```
True
False
```

---

## 16. Binary Search

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

## 17. Merge Two Sorted Arrays

```python
arr1, arr2 = [1,3,5], [2,4,6]
merged = []
i = j = 0
while i < len(arr1) and j < len(arr2):
    if arr1[i] < arr2[j]:
        merged.append(arr1[i]); i+=1
    else:
        merged.append(arr2[j]); j+=1
merged.extend(arr1[i:])
merged.extend(arr2[j:])
print(merged)
```

**Output:**

```
[1, 2, 3, 4, 5, 6]
```

---

## 18. Matrix Transpose

```python
matrix = 1,2,3],[4,5,6
transpose = [[row[i] for row in matrix] for i in range(len(matrix[0]))]
print(transpose)
```

**Output:**

```
1, 4], [2, 5], [3, 6
```

---

## 19. Matrix Multiplication

```python
A = 1,2],[3,4
B = 5,6],[7,8
result = 0,0],[0,0

for i in range(len(A)):
    for j in range(len(B[0])):
        for k in range(len(B)):
            result[i][j] += A[i][k] * B[k][j]

print(result)
```

**Output:**

```
19, 22], [43, 50
```

---

## 20. Find Subarray with Given Sum

```python
def subarray_sum(arr, target):
    s = 0
    d = {0:-1}
    for i, num in enumerate(arr):
        s += num
        if s-target in d:
            return (d[s-target]+1, i)
        d[s] = i
    return None

print(subarray_sum([1,2,3,7,5], 12))
```

**Output:**

```
(1, 3)
```

---

## 21. Find All Substrings

```python
s = "abc"
subs = [s[i:j] for i in range(len(s)) for j in range(i+1,len(s)+1)]
print(subs)
```

**Output:**

```
['a', 'ab', 'abc', 'b', 'bc', 'c']
```

---

## 22. Rotate Array by k

```python
arr = [1,2,3,4,5,6,7]
k = 3
rotated = arr[-k:] + arr[:-k]
print(rotated)
```

**Output:**

```
[5, 6, 7, 1, 2, 3, 4]
```

---

## 23. Longest Common Prefix

```python
def longest_common_prefix(strs):
    if not strs: return ""
    prefix = strs[0]
    for s in strs[1:]:
        while not s.startswith(prefix):
            prefix = prefix[:-1]
    return prefix

print(longest_common_prefix(["flower","flow","flight"]))
```

**Output:**

```
fl
```

---

## 24. Find Majority Element

```python
def majority_element(nums):
    count, candidate = 0, None
    for num in nums:
        if count == 0:
            candidate = num
        count += (1 if num == candidate else -1)
    return candidate

print(majority_element([3,3,4,2,3,3,5]))
```

**Output:**

```
3
```

---

## 25. Kadane’s Algorithm (Max Subarray Sum)

```python
def max_subarray(arr):
    max_sum = curr = arr[0]
    for num in arr[1:]:
        curr = max(num, curr+num)
        max_sum = max(max_sum, curr)
    return max_sum

print(max_subarray([-2,1,-3,4,-1,2,1,-5,4]))
```

**Output:**

```
6
```

**Explanation:** Subarray `[4,-1,2,1]` ka sum maximum hai.

---

✅ **Ab tak total: 70+ problems ho gaye (Basic → Advanced → Interview Level).**
Agla part (📘 Part 4E) me main **System Design Level Python Questions, Mini Projects, Decorators, Generators, Multithreading, AsyncIO** cover kar sakta hu.

---

👉 Kya tum chahte ho ki **Part 4E** me mai **real-world mini-projects (like Todo App CLI, File Organizer, Web Scraper)** add karu ya **sirf advanced interview-level tricky questions** du?


