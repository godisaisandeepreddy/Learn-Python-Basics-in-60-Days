
A **lambda function** is a small, anonymous (unnamed) function defined with the keyword `lambda`.  
It’s useful when you need a **quick, throwaway function** for short tasks.

---

## 1️⃣ Syntax

```python
lambda arguments: expression
```

- Takes any number of arguments.
    
- Has only **one expression** (executed & returned).
    
- No `return` keyword needed.
    

---

## 2️⃣ Basic Example

```python
# Normal function
def add(x, y):
    return x + y

# Lambda equivalent
add_lambda = lambda x, y: x + y

print(add(5, 3))        # 8
print(add_lambda(5, 3)) # 8
```

---

## 3️⃣ Why Use Lambda?

- To define **short functions inline**.
    
- Often used with higher-order functions like `map()`, `filter()`, `sorted()`.
    
- Helps keep code concise.
    

---

## 4️⃣ Examples

### ✅ Single argument

```python
square = lambda x: x * x
print(square(4))  # 16
```

---

### ✅ Multiple arguments

```python
multiply = lambda a, b, c: a * b * c
print(multiply(2, 3, 4))  # 24
```

---

### ✅ No arguments

```python
say_hello = lambda: "Hello, Python!"
print(say_hello())  # Hello, Python!
```

---

## 5️⃣ Using `lambda` with Built-in Functions

### 🔹 `map()` – Apply function to each element

```python
nums = [1, 2, 3, 4, 5]
squares = list(map(lambda x: x**2, nums))
print(squares)  # [1, 4, 9, 16, 25]
```

---

### 🔹 `filter()` – Keep elements that satisfy condition

```python
nums = [10, 15, 20, 25, 30]
evens = list(filter(lambda x: x % 2 == 0, nums))
print(evens)  # [10, 20, 30]
```

---

### 🔹 `sorted()` – Custom sorting

```python
words = ["banana", "apple", "cherry", "date"]
sorted_words = sorted(words, key=lambda x: len(x))
print(sorted_words)  # ['date', 'apple', 'banana', 'cherry']
```

---

### 🔹 `reduce()` – Accumulate values (from `functools`)

```python
from functools import reduce

nums = [1, 2, 3, 4, 5]
product = reduce(lambda x, y: x * y, nums)
print(product)  # 120
```

---

## 6️⃣ Nested Lambda

```python
double_then_add = lambda x: (lambda y: x + y)(x * 2)
print(double_then_add(5))  # 15
```

---

## 7️⃣ Limitations of Lambda

- Only **one expression** allowed (no statements, loops, assignments).
    
- Harder to debug than named functions.
    
- Use only for **small, quick tasks** → for bigger logic, stick to `def`.
    

---

## 8️⃣ Best Practices

✅ Use lambda for **short helper functions**.  
✅ Combine with `map()`, `filter()`, `sorted()`, `reduce()`.  
❌ Don’t replace normal functions if logic is complex → code readability suffers.

---

## 9️⃣ Exercises

1. Write a lambda function to calculate the cube of a number.
    
2. Use `map()` + lambda to convert a list of temperatures from Celsius → Fahrenheit.
    
3. Use `filter()` + lambda to extract all odd numbers from `[1, 2, 3, ..., 20]`.
    
4. Use `sorted()` + lambda to sort a list of tuples by the **second element**.  
    Example: `[(1, 5), (2, 2), (3, 8)] → [(2, 2), (1, 5), (3, 8)]`
    
5. Use `reduce()` + lambda to find the **sum of squares** of numbers `[1, 2, 3, 4]`.
    

---

✅ By end of Day 12 → You’ll be comfortable using **lambda functions** in real Python tasks, especially with higher-order functions.

---
