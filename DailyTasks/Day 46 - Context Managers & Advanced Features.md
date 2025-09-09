
---

## 1️⃣ `with` Statement & Context Managers

A **context manager** is used with the `with` statement to manage resources (like files, DB connections, network sockets).

- Needs two special methods:
    
    - `__enter__` → setup
        
    - `__exit__` → cleanup
        

Example:

```python
class FileOpener:
    def __init__(self, filename):
        self.filename = filename

    def __enter__(self):
        self.file = open(self.filename, "r")
        return self.file

    def __exit__(self, exc_type, exc_val, exc_tb):
        self.file.close()
        print("File closed")

# Usage
with FileOpener("sample.txt") as f:
    print(f.read())
```

✔ Automatically closes file even if an error occurs inside the block.

---

## 2️⃣ Using `contextlib.contextmanager`

Instead of defining a class, Python provides a **decorator-based shortcut**:

```python
from contextlib import contextmanager

@contextmanager
def open_file(name):
    f = open(name, "r")
    try:
        yield f   # resource available here
    finally:
        f.close()
        print("File closed")

# Usage
with open_file("sample.txt") as f:
    print(f.read())
```

---

## 3️⃣ Abstract Base Classes (`abc` module)

- Abstract Base Classes allow you to **enforce a contract** (like interfaces in Java).
    
- You can’t instantiate abstract classes directly.
    
- Child classes must implement abstract methods.
    

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, r): self.r = r
    def area(self): return 3.14 * self.r * self.r

# s = Shape()   # ❌ TypeError
c = Circle(5)
print(c.area())  # ✅ 78.5
```

✔ Used in large projects to enforce consistent APIs across subclasses.

---

## 4️⃣ 🏋️ Exercise – Context Manager Timer

👉 Create a context manager that times how long a block of code runs.

```python
import time

class Timer:
    def __enter__(self):
        self.start = time.time()
        return self
    def __exit__(self, exc_type, exc_val, exc_tb):
        self.end = time.time()
        print(f"Elapsed time: {self.end - self.start:.5f} sec")

# Usage
with Timer():
    total = 0
    for i in range(10**6):
        total += i
    print("Loop finished")
```

✅ Output:

```
Loop finished
Elapsed time: 0.12045 sec
```

---

📌 With this, you now know:

- Custom context managers (`__enter__` / `__exit__`)
    
- `contextlib.contextmanager` for cleaner syntax
    
- Abstract Base Classes for structured OOP
    

---
