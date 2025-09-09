
The `functools` module provides **higher-order functions and utilities** that help in **functional programming style** in Python.

---

## 1️⃣ `reduce()` – Cumulative Function Application

- Repeatedly applies a function to items in an iterable.
    
- Useful for cumulative operations (like sum, product, max, etc.).
    

```python
from functools import reduce

nums = [1, 2, 3, 4]

# Sum using reduce
total = reduce(lambda x, y: x + y, nums)
print(total)  # 10

# Product using reduce
product = reduce(lambda x, y: x * y, nums)
print(product)  # 24
```

⚡ Note: `sum(nums)` is simpler, but `reduce` shines for **custom accumulations**.

---

## 2️⃣ `partial()` – Fixing Function Arguments

- Creates a **new function with some arguments pre-filled**.
    

```python
from functools import partial

def power(base, exp):
    return base ** exp

# Pre-fix exponent to 2 → creates "square"
square = partial(power, exp=2)
cube = partial(power, exp=3)

print(square(5))  # 25
print(cube(3))    # 27
```

📌 Use when you call the same function often with fixed parameters.

---

## 3️⃣ `lru_cache()` – Caching Function Results

- **Memoization**: stores function results so repeated calls are fast.
    
- Extremely useful for **recursive functions**.
    

```python
from functools import lru_cache

@lru_cache(maxsize=None)  # unlimited cache
def fib(n):
    if n < 2:
        return n
    return fib(n-1) + fib(n-2)

print(fib(50))  # very fast!
```

⏱ Without cache, computing `fib(50)` takes a long time. With cache, it’s almost instant.

---

## 4️⃣ `wraps()` – Preserving Function Metadata

When writing decorators, the wrapped function may lose its original **name and docstring**.  
`functools.wraps` fixes this.

```python
from functools import wraps

def my_decorator(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        """Wrapper function"""
        print("Before function call")
        result = func(*args, **kwargs)
        print("After function call")
        return result
    return wrapper

@my_decorator
def greet(name):
    """Greet someone"""
    print(f"Hello, {name}!")

print(greet.__name__)   # greet (without wraps: wrapper)
print(greet.__doc__)    # Greet someone
```

---

## 5️⃣ Exercises

### 🔹 Exercise 1

Write a recursive factorial function and use `lru_cache` to speed it up.

```python
from functools import lru_cache

@lru_cache(maxsize=None)
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n-1)

print(factorial(10))   # 3628800
print(factorial(50))   # works instantly!
```

### 🔹 Exercise 2

Use `reduce()` to:

- Find the maximum number in a list.
    
- Concatenate a list of strings.
    

### 🔹 Exercise 3

Use `partial()` to create:

- A function `double(x)` that always multiplies by 2.
    
- A function `increment(x)` that always adds 1.
    

---

✅ By the end of **Day 18** → You’ll understand **functional programming helpers in `functools`**, and how they make recursion, decorators, and parameter handling much easier.

---
