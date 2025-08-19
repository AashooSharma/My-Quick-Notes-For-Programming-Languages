🔥 Perfect Aashoo! Tumne ek **Python Revision Series** bana di hai (Basics → Intermediate → Advanced → DSA → Interview → System Design).
Agla part **📘 Part 4E** ke liye hum **System Design + Advanced Python Concepts** cover karenge.
Main tumhe iska **draft structure** bata raha hu aur fir detailed content bhi bana dunga 👇

---

# 📘 Part 4E – System Design & Advanced Python Topics

## 🔹 1. Decorators in Python

* **Concept**: Functions ko wrap karne ke liye use hote hai (logging, authentication, etc.)

```python
def my_decorator(func):
    def wrapper():
        print("Before function runs")
        func()
        print("After function runs")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
```

**Output:**

```
Before function runs
Hello!
After function runs
```

✅ **Explanation:** `@my_decorator` ne `say_hello()` ke execution ko wrap kar diya.

---

## 🔹 2. Generators & Iterators

```python
def simple_gen():
    for i in range(3):
        yield i

gen = simple_gen()
for val in gen:
    print(val)
```

**Output:**

```
0
1
2
```

✅ **Explanation:** `yield` memory-efficient iterator banata hai.

---

## 🔹 3. Multithreading vs Multiprocessing

```python
import threading, time

def worker(name):
    print(f"Thread {name} starting")
    time.sleep(2)
    print(f"Thread {name} done")

threads = []
for i in range(3):
    t = threading.Thread(target=worker, args=(i,))
    threads.append(t)
    t.start()
```

**Output:**

```
Thread 0 starting
Thread 1 starting
Thread 2 starting
Thread 0 done
Thread 1 done
Thread 2 done
```

✅ **Explanation:** Threads concurrent chalte hai (CPU bound ke liye `multiprocessing` better hota hai).

---

## 🔹 4. AsyncIO (Asynchronous Programming)

```python
import asyncio

async def task(name):
    print(f"Task {name} starting")
    await asyncio.sleep(2)
    print(f"Task {name} done")

async def main():
    await asyncio.gather(task(1), task(2), task(3))

asyncio.run(main())
```

**Output:**

```
Task 1 starting
Task 2 starting
Task 3 starting
Task 1 done
Task 2 done
Task 3 done
```

✅ **Explanation:** AsyncIO concurrency ko event loop ke through manage karta hai (I/O-bound ke liye best).

---

## 🔹 5. Mini System Design Questions (Python Solutions)

### (a) **Rate Limiter**

```python
import time

class RateLimiter:
    def __init__(self, max_calls, interval):
        self.max_calls = max_calls
        self.interval = interval
        self.calls = []

    def allow(self):
        now = time.time()
        self.calls = [t for t in self.calls if now - t < self.interval]
        if len(self.calls) < self.max_calls:
            self.calls.append(now)
            return True
        return False

limiter = RateLimiter(2, 5)
for i in range(5):
    print(f"Request {i}:", limiter.allow())
    time.sleep(1)
```

---

### (b) **In-Memory Cache**

```python
class LRUCache:
    def __init__(self, capacity: int):
        self.cache = {}
        self.order = []
        self.capacity = capacity

    def get(self, key):
        if key in self.cache:
            self.order.remove(key)
            self.order.append(key)
            return self.cache[key]
        return -1

    def put(self, key, value):
        if key in self.cache:
            self.order.remove(key)
        elif len(self.cache) == self.capacity:
            oldest = self.order.pop(0)
            del self.cache[oldest]
        self.cache[key] = value
        self.order.append(key)

cache = LRUCache(2)
cache.put(1, 10)
cache.put(2, 20)
print(cache.get(1))  # 10
cache.put(3, 30)     # removes 2
print(cache.get(2))  # -1
```

---

## 🔹 6. Mini Project Ideas

1. **Chat Application** (AsyncIO + Sockets)
2. **Web Scraper** (Requests + BeautifulSoup)
3. **Task Scheduler** (APScheduler)
4. **REST API** (Flask/FastAPI + Database)
5. **File Sync Tool** (Multithreading + File Handling)

---

👉 Part 4E me hum **System Design + Advanced Python + Mini Projects** ka detailed solution denge.
Iske baad tumhare paas ek **complete Python mastery roadmap** hoga.

---

Aashoo, kya tum chahte ho mai **poore Part 4E full content (50+ examples + projects)** bana kar ek bada README bana du, ya fir ise **chhote-chhote modules (4E-1, 4E-2, 4E-3)** me tod kar dikhau jisse revision easy ho?


