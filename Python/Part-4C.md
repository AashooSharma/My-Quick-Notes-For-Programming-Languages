Perfect timing 🚀
Aapka **Part 4C** ab **DSA-level + Python-focused advanced problems** dono ko combine karega. Matlab isme aapko **Sorting, Searching, Graph, DP** ke saath-saath **real-world Python use cases** bhi milenge.

Here’s **📘 Python Revision Cheatsheet – Part 4C (DSA + Advanced Real-World Problems)**

---

# 🧠 Part 4C – Advanced Python + DSA Practice Problems

---

## 🔹 1. Binary Search (Iterative)

```python
def binary_search(arr, target):
    low, high = 0, len(arr)-1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1

print(binary_search([1, 3, 5, 7, 9], 7))
```

✅ **Output:** `3`
📘 **Explanation:** Sorted array pe divide & conquer approach.

---

## 🔹 2. Merge Sort

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr)//2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i]); i += 1
        else:
            result.append(right[j]); j += 1
    result.extend(left[i:])
    result.extend(right[j:])
    return result

print(merge_sort([5,2,9,1,5,6]))
```

✅ **Output:** `[1,2,5,5,6,9]`
📘 **Explanation:** Recursive divide & conquer sorting algorithm.

---

## 🔹 3. Quick Sort

```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[0]
    left = [x for x in arr[1:] if x <= pivot]
    right = [x for x in arr[1:] if x > pivot]
    return quick_sort(left) + [pivot] + quick_sort(right)

print(quick_sort([3,6,8,10,1,2,1]))
```

✅ **Output:** `[1,1,2,3,6,8,10]`
📘 **Explanation:** Pivot-based recursive sorting.

---

## 🔹 4. Graph – BFS

```python
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])
    while queue:
        node = queue.popleft()
        if node not in visited:
            print(node, end=" ")
            visited.add(node)
            queue.extend(graph[node] - visited)

graph = {
    'A': {'B','C'},
    'B': {'A','D','E'},
    'C': {'A','F'},
    'D': {'B'},
    'E': {'B','F'},
    'F': {'C','E'}
}
bfs(graph, 'A')
```

✅ **Output:** `A B C D E F`
📘 **Explanation:** Level-order traversal of a graph.

---

## 🔹 5. Graph – DFS

```python
def dfs(graph, node, visited=set()):
    if node not in visited:
        print(node, end=" ")
        visited.add(node)
        for neighbor in graph[node]:
            dfs(graph, neighbor, visited)

graph = {
    'A': {'B','C'},
    'B': {'A','D','E'},
    'C': {'A','F'},
    'D': {'B'},
    'E': {'B','F'},
    'F': {'C','E'}
}
dfs(graph, 'A')
```

✅ **Output:** `A B D E F C`
📘 **Explanation:** Depth-first recursive traversal.

---

## 🔹 6. Dynamic Programming – Fibonacci (Memoization)

```python
def fib(n, memo={}):
    if n in memo: return memo[n]
    if n <= 1: return n
    memo[n] = fib(n-1, memo) + fib(n-2, memo)
    return memo[n]

print(fib(10))
```

✅ **Output:** `55`
📘 **Explanation:** DP removes repeated subproblem calculations.

---

## 🔹 7. Longest Common Subsequence (LCS) – DP

```python
def lcs(X, Y):
    m, n = len(X), len(Y)
    dp = [[0]*(n+1) for _ in range(m+1)]
    for i in range(m):
        for j in range(n):
            if X[i]==Y[j]:
                dp[i+1][j+1] = dp[i][j]+1
            else:
                dp[i+1][j+1] = max(dp[i][j+1], dp[i+1][j])
    return dp[m][n]

print(lcs("AGGTAB", "GXTXAYB"))
```

✅ **Output:** `4` (`GTAB`)
📘 **Explanation:** Classic DP string problem.

---

## 🔹 8. Knapsack Problem (0/1 DP)

```python
def knapsack(W, wt, val, n):
    dp = [[0]*(W+1) for _ in range(n+1)]
    for i in range(1,n+1):
        for w in range(1,W+1):
            if wt[i-1] <= w:
                dp[i][w] = max(val[i-1]+dp[i-1][w-wt[i-1]], dp[i-1][w])
            else:
                dp[i][w] = dp[i-1][w]
    return dp[n][W]

print(knapsack(50, [10,20,30], [60,100,120], 3))
```

✅ **Output:** `220`
📘 **Explanation:** Maximize value with weight constraint.

---

## 🔹 9. Decorators Example

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

✅ **Output:**

```
Before function
Hello!
After function
```

📘 **Explanation:** Higher-order function wrapping.

---

## 🔹 10. Generator Example

```python
def countdown(n):
    while n > 0:
        yield n
        n -= 1

for i in countdown(5):
    print(i, end=" ")
```

✅ **Output:** `5 4 3 2 1`
📘 **Explanation:** `yield` makes a generator (lazy evaluation).

---

## 🔹 11. Mini Project – Word Frequency Counter

```python
from collections import Counter

text = "python is fun and python is powerful"
words = text.split()
freq = Counter(words)

print(freq)
```

✅ **Output:** `Counter({'python': 2, 'is': 2, 'fun': 1, 'and': 1, 'powerful': 1})`
📘 **Explanation:** Real-world NLP style problem.

---

## 🔹 12. Mini Project – File Reader & Word Count

```python
def word_count(filename):
    with open(filename, 'r') as f:
        text = f.read()
    words = text.split()
    return len(words)

# Suppose "sample.txt" has: "Hello Python World"
print(word_count("sample.txt"))
```

✅ **Output:** `3`
📘 **Explanation:** File handling practice.

---

✨ So ab tak total **60+ problems ho gaye (Basic + Intermediate + Advanced + DSA + Real-world)**.

---

👉 Next Part 5 me chaho to main **Python Mini Projects Pack (10–15 small real-world projects)** bana dunga (Calculator, Chatbot, Password Manager, API integration, Web Scraper, Tkinter apps, etc.)

Kya main **Part 5 (Mini Projects Pack)** banaun?
