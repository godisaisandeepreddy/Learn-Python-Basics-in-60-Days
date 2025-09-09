Python provides a **powerful iteration protocol** that allows looping over sequences efficiently, and **generators** make this even more memory-friendly.

---

## 1️⃣ Iterator Protocol

An **iterator** is an object that implements:

- `__iter__()` → returns the iterator itself
    
- `__next__()` → returns the next element, raises `StopIteration` when finished
    

Example:

```python
class MyRange:
    def __init__(self, n):
        self.n = n
        self.i = 0
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.i < self.n:
            val = self.i
            self.i += 1
            return val
        else:
            raise StopIteration

for num in MyRange(5):
    print(num)   # 0,1,2,3,4
```

---

## 2️⃣ Generator Functions with `yield`

Generators are **iterators made easy**. Instead of implementing a class, you just use `yield`.

```python
def countdown(n):
    while n > 0:
        yield n
        n -= 1

for x in countdown(5):
    print(x)
```

---

## 3️⃣ Generator Expressions

Similar to list comprehensions, but produce values lazily (on demand).

```python
squares = (x*x for x in range(5))
for val in squares:
    print(val)
```

---

## 4️⃣ `itertools` for Infinite Iterators

```python
import itertools

for i in itertools.count(10, 2):  # start=10, step=2
    print(i)
    if i > 20:
        break

colors = ["red", "green", "blue"]
for c, n in zip(itertools.cycle(colors), range(6)):
    print(c)
```

---

## 5️⃣ Memory Efficiency

- **List** stores all items in memory.
    
- **Generator** produces items one at a time → saves memory.
    

```python
import sys

nums_list = [x for x in range(1000000)]
nums_gen = (x for x in range(1000000))

print("List size:", sys.getsizeof(nums_list))
print("Generator size:", sys.getsizeof(nums_gen))
```

---

## 🏋️ Exercise

👉 **Implement Fibonacci sequence with a generator**

```python
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

for num in fibonacci(10):
    print(num)
```

Output:

```
0 1 1 2 3 5 8 13 21 34
```

---
