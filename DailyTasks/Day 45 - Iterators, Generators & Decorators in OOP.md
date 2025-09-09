
---

## 1️⃣ Making Classes Iterable (`__iter__`, `__next__`)

To make a class **iterable** (usable in a `for` loop):

- Define `__iter__()` → returns an **iterator object** (usually `self`)
    
- Define `__next__()` → returns next value, or raises `StopIteration`
    

```python
class Countdown:
    def __init__(self, start):
        self.start = start
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.start <= 0:
            raise StopIteration
        value = self.start
        self.start -= 1
        return value

for num in Countdown(5):
    print(num)   # 5,4,3,2,1
```

---

## 2️⃣ Generators Inside Classes

Instead of writing `__iter__` + `__next__`, you can use a **generator function** inside a class:

```python
class Countdown:
    def __init__(self, start):
        self.start = start
    
    def __iter__(self):
        n = self.start
        while n > 0:
            yield n
            n -= 1

for num in Countdown(5):
    print(num)
```

✔ Much cleaner and still fully iterable.

---

## 3️⃣ Function Decorators in OOP

### 🔹 `@staticmethod`

- Belongs to class, doesn’t need `self`
    
- Utility function grouped inside class
    

```python
class Math:
    @staticmethod
    def add(a, b):
        return a + b

print(Math.add(5, 3))  # 8
```

---

### 🔹 `@classmethod`

- Receives `cls` (class itself)
    
- Often used for **alternative constructors**
    

```python
class Person:
    def __init__(self, name):
        self.name = name
    
    @classmethod
    def from_string(cls, s):
        return cls(s.title())

p = Person.from_string("alice")
print(p.name)  # Alice
```

---

## 4️⃣ Custom Decorators

A **decorator** wraps another function to add extra behavior.

```python
def log(func):
    def wrapper(*a, **kw):
        print("Calling", func.__name__)
        return func(*a, **kw)
    return wrapper

@log
def greet():
    print("Hello")

greet()
# Calling greet
# Hello
```

---

## 5️⃣ 🏋️ Exercise – Execution Time Decorator

👉 Create a decorator to **measure execution time of methods**.

```python
import time

def measure_time(func):
    def wrapper(*a, **kw):
        start = time.time()
        result = func(*a, **kw)
        end = time.time()
        print(f"{func.__name__} took {end - start:.5f} sec")
        return result
    return wrapper

class MathOps:
    @measure_time
    def slow_square(self, n):
        time.sleep(1)  # simulate slow work
        return n * n

m = MathOps()
print(m.slow_square(5))
```

✅ Output:

```
slow_square took 1.00012 sec
25
```

---
