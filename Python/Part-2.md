# 🐍 Python Syntax & Examples Cheat Sheet (Part 2 – Advanced)

This is the **next part** of the Python syntax revision guide. It covers advanced topics, more libraries, and missing concepts.

---

## 15. Iterators & Itertools

### Iterators

```python
nums = [1, 2, 3]
it = iter(nums)
print(next(it))  # 1
print(next(it))  # 2
```

### Itertools Examples

```python
import itertools

# Infinite counter
for i in itertools.count(5, 2):
    if i > 10:
        break
    print(i)
```

**Output:** `5 7 9`

```python
# Combinations
from itertools import combinations
print(list(combinations([1,2,3], 2)))
```

**Output:** `[(1,2), (1,3), (2,3)]`

---

## 16. Regular Expressions (re module)

```python
import re
pattern = r"[a-z]+"
text = "hello 123 world"

matches = re.findall(pattern, text)
print(matches)
```

**Output:** `["hello", "world"]`

```python
match = re.search(r"world", text)
print(match.start(), match.end())
```

**Output:** `10 15`

---

## 17. JSON Handling

```python
import json

# Dictionary → JSON string
data = {"name": "Aashoo", "age": 24}
json_str = json.dumps(data)
print(json_str)

# JSON string → Dictionary
parsed = json.loads(json_str)
print(parsed["name"])
```

**Output:**

```
{"name": "Aashoo", "age": 24}
Aashoo
```

---

## 18. OS & Sys Module

```python
import os
print(os.name)       # nt (on Windows)
print(os.getcwd())   # current working directory

# List files
print(os.listdir("."))
```

```python
import sys
print(sys.version)   # Python version
print(sys.argv)      # Command-line arguments
```

---

## 19. Random Module

```python
import random
print(random.randint(1, 10))   # random int 1–10
print(random.choice(["a", "b", "c"]))
print(random.sample(range(10), 3))
```

---

## 20. Collections Module

```python
from collections import Counter, defaultdict, deque

# Counter
print(Counter("banana"))  # {'a':3, 'b':1, 'n':2}

# Defaultdict
nums = defaultdict(int)
nums["a"] += 1
print(nums)

# Deque
q = deque([1,2,3])
q.appendleft(0)
q.append(4)
print(q)
```

---

## 21. Datetime & Time

```python
from datetime import datetime, timedelta

now = datetime.now()
print(now.strftime("%Y-%m-%d %H:%M:%S"))

future = now + timedelta(days=5)
print(future)
```

```python
import time
print("Sleeping...")
time.sleep(2)
print("Awake!")
```

---

## 22. Advanced Functions

### \*args and \*\*kwargs

```python
def func(*args, **kwargs):
    print(args)
    print(kwargs)

func(1,2,3, name="Aashoo", age=24)
```

**Output:** `(1,2,3)` and `{ 'name': 'Aashoo', 'age':24 }`

### Map, Filter, Reduce

```python
nums = [1,2,3,4]
print(list(map(lambda x: x*2, nums)))
print(list(filter(lambda x: x%2==0, nums)))

from functools import reduce
print(reduce(lambda a,b: a+b, nums))
```

**Output:** `[2,4,6,8] [2,4] 10`

---

## 23. Virtual Environments

```bash
# Create venv
python -m venv myenv

# Activate
# Windows:
myenv\Scripts\activate
# Linux/Mac:
source myenv/bin/activate

# Deactivate
 deactivate
```

---

## 24. Pip & Package Management

```bash
pip install requests
pip freeze > requirements.txt
pip install -r requirements.txt
```

---

## 25. Popular Libraries Quick Start

### Requests (HTTP)

```python
import requests
response = requests.get("https://jsonplaceholder.typicode.com/todos/1")
print(response.json())
```

### Pandas (Data Handling)

```python
import pandas as pd

df = pd.DataFrame({"name":["Aashoo","Sharma"], "age":[24,25]})
print(df)
```

### NumPy (Math)

```python
import numpy as np
arr = np.array([1,2,3])
print(arr.mean())
```

### Matplotlib (Plotting)

```python
import matplotlib.pyplot as plt
plt.plot([1,2,3],[4,5,6])
plt.show()
```

---

# ✅ Summary (Part 2)

* Covered advanced standard libraries (re, json, os, sys, collections, datetime, itertools).
* Learned functional programming tools (map, filter, reduce, \*args, \*\*kwargs).
* Quick start with requests, pandas, numpy, matplotlib.
* Next expansion can include: **asyncio, threading, multiprocessing, SQLAlchemy, Flask, Django basics**.



