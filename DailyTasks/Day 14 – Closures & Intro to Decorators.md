Closures and decorators are **advanced function concepts** that build on what you’ve learned about functions, scopes, and higher-order functions.

---

## 1️⃣ Closures

A **closure** is a function that:

- Is defined **inside another function** (nested function).
    
- **Remembers the variables** from its enclosing scope, even after the outer function has finished executing.
    

👉 This allows functions to carry some "state".

---

### Example 1 – Simple Closure

```python
def outer_function(msg):
    def inner_function():
        print("Message:", msg)  # remembers 'msg'
    return inner_function

greet = outer_function("Hello Python")
greet()  # Message: Hello Python
```

- `outer_function` finished execution.
    
- But `inner_function` **remembers `msg`** (closure).
    

---

### Example 2 – Counter with Closure

```python
def make_counter():
    count = 0
    def counter():
        nonlocal count
        count += 1
        return count
    return counter

c1 = make_counter()
print(c1())  # 1
print(c1())  # 2
print(c1())  # 3
```

Here:

- Each call updates `count`.
    
- The state is preserved inside closure.
    

---

### Example 3 – Function Factory

```python
def power_of(n):
    def inner(x):
        return x ** n
    return inner

square = power_of(2)
cube = power_of(3)

print(square(5))  # 25
print(cube(2))    # 8
```

---

## 2️⃣ Why Closures Are Useful

- Helps in **data hiding** (keeping state private).
    
- Useful in **decorators** (next section).
    
- Great for writing **function factories**.
    

---

## 3️⃣ Intro to Decorators

A **decorator** is a special function that:

- **Takes another function as input**.
    
- Adds extra behavior **without modifying the original function**.
    
- Returns a new function.
    

👉 Decorators are built using **closures**.

---

### Example 1 – Manual Decorator

```python
def decorator_function(func):
    def wrapper():
        print("Before function call")
        func()
        print("After function call")
    return wrapper

def say_hello():
    print("Hello!")

decorated = decorator_function(say_hello)
decorated()
```

✅ Output:

```
Before function call
Hello!
After function call
```

---

### Example 2 – Using `@` Syntax

Instead of manually wrapping:

```python
def decorator_function(func):
    def wrapper():
        print("Before function call")
        func()
        print("After function call")
    return wrapper

@decorator_function
def say_hi():
    print("Hi!")

say_hi()
```

✅ Output:

```
Before function call
Hi!
After function call
```

---

### Example 3 – Decorator with Arguments

```python
def logger(func):
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__} with {args}, {kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} returned {result}")
        return result
    return wrapper

@logger
def add(a, b):
    return a + b

add(5, 3)
```

✅ Output:

```
Calling add with (5, 3), {}
add returned 8
```

---

## 4️⃣ Key Points

- **Closures** → Function + enclosed variables.
    
- **Decorators** → Functions that modify/enhance other functions.
    
- Built-in decorators exist in Python (`@staticmethod`, `@classmethod`, `@property`).
    

---

## 5️⃣ Exercises

1. Create a closure that generates a function to multiply any number by a fixed multiplier (like `double = multiplier(2)`).
    
2. Create a closure that maintains a running total (like a mini calculator).
    
3. Write a decorator that measures the **execution time** of a function.
    
4. Write a decorator that only allows a function to run if the user is `"admin"`.
    
5. Write a decorator that retries a function **3 times** if it raises an exception.
    

---

✅ By end of Day 14 → You’ll have mastered **closures and decorators**, which are foundational for advanced Python (Flask, Django, FastAPI, Pandas, etc. use decorators heavily).

---
