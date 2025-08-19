# Python Syntax Cheat Sheet - Part 3 (Expanded with Practice Problems)

This section focuses on **practice coding problems** with explanations and outputs. These are great for revision and improving problem-solving skills.

---

## 1. Print a Square Pattern

```python
# Print a square of size 5x5 with '*'
n = 5
for i in range(n):
    for j in range(n):
        print('*', end=' ')
    print()
```

### Output:

```
* * * * *
* * * * *
* * * * *
* * * * *
* * * * *
```

### Explanation:

* Outer loop → rows
* Inner loop → columns
* `end=' '` prevents moving to a new line

---

## 2. Print a Right-Angled Triangle

```python
n = 5
for i in range(1, n+1):
    print('*' * i)
```

### Output:

```
*
**
***
****
*****
```

### Explanation:

* `print('*' * i)` multiplies `*` by the loop index → increases stars each row.

---

## 3. Inverted Right-Angled Triangle

```python
n = 5
for i in range(n, 0, -1):
    print('*' * i)
```

### Output:

```
*****
****
***
**
*
```

### Explanation:

* Loop runs backward from 5 → 1.

---

## 4. Pyramid Pattern

```python
n = 5
for i in range(n):
    print(' ' * (n-i-1) + '*' * (2*i+1))
```

### Output:

```
    *
   ***
  *****
 *******
*********
```

### Explanation:

* Spaces (`' ' * (n-i-1)`) align the stars.
* Stars (`'*' * (2*i+1)`) increase by 2 each row.

---

## 5. Diamond Pattern

```python
n = 5
# Upper half
for i in range(n):
    print(' ' * (n-i-1) + '*' * (2*i+1))
# Lower half
for i in range(n-2, -1, -1):
    print(' ' * (n-i-1) + '*' * (2*i+1))
```

### Output:

```
    *
   ***
  *****
 *******
*********
 *******
  *****
   ***
    *
```

### Explanation:

* First loop → pyramid.
* Second loop → inverted pyramid.

---

## 6. Hollow Square

```python
n = 5
for i in range(n):
    for j in range(n):
        if i == 0 or i == n-1 or j == 0 or j == n-1:
            print('*', end=' ')
        else:
            print(' ', end=' ')
    print()
```

### Output:

```
* * * * *
*       *
*       *
*       *
* * * * *
```

### Explanation:

* Border → `*`
* Inside → spaces

---

## 7. Number Pyramid

```python
n = 5
for i in range(1, n+1):
    print(' ' * (n-i) + ' '.join(str(j) for j in range(1, i+1)))
```

### Output:

```
    1
   1 2
  1 2 3
 1 2 3 4
1 2 3 4 5
```

---

## 8. Circle-Like Pattern (Approximation)

```python
import math
radius = 5
for i in range((2*radius)+1):
    for j in range((2*radius)+1):
        distance = math.sqrt((i-radius)**2 + (j-radius)**2)
        if distance < radius+0.5 and distance > radius-0.5:
            print('*', end=' ')
        else:
            print(' ', end=' ')
    print()
```

### Output:

```
    *****
  *     *
 *       *
*         *
 *       *
  *     *
    *****
```

### Explanation:

* Uses circle equation `(x-h)² + (y-k)² = r²`.
* Approximates circle with `*`.

---

## Notes:

✔ These patterns strengthen logic for loops and conditions.
✔ Common in interviews & practice tests.
✔ Modify `n` to change size.

---

➡️ Next Part (Part 4) will include **problem-solving challenges (Fibonacci, Prime, Factorial, etc.)** with solutions.


