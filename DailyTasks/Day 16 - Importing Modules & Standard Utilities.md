
---

## 1️⃣ What are Modules?

- A **module** is a file containing Python code (functions, classes, variables).
    
- Helps in **organizing code** and **reusing functionality**.
    

### 🔹 Built-in modules:

Python ships with many useful modules (`math`, `random`, `datetime`, `os`, etc.).

### 🔹 User-defined modules:

You can also create your own `.py` file and import it.

---

## 2️⃣ Importing Modules

Different ways:

```python
# Import whole module
import math
print(math.sqrt(25))   # 5.0

# Import specific function
from math import sqrt
print(sqrt(25))        # 5.0

# Import with alias
import math as m
print(m.sqrt(25))      # 5.0
```

✅ Use **alias** (`as`) when module names are long.  
✅ Use `from ... import ...` for selective imports.

---

## 3️⃣ The `math` Module

Provides mathematical operations.

```python
import math

print(math.pi)             # 3.141592653589793
print(math.e)              # 2.718281828459045
print(math.sqrt(16))       # 4.0
print(math.factorial(5))   # 120
print(math.ceil(4.3))      # 5
print(math.floor(4.7))     # 4
print(math.pow(2, 3))      # 8.0
```

---

## 4️⃣ The `random` Module

Used for generating random numbers.

```python
import random

print(random.randint(1, 6))     # Random integer between 1 and 6
print(random.choice(["red", "green", "blue"]))  # Randomly pick one
print(random.random())          # Random float between 0 and 1
print(random.uniform(5, 10))    # Random float between 5 and 10
```

---

## 5️⃣ The `datetime` Module

Used for working with dates and times.

```python
from datetime import datetime, timedelta

# Current date & time
now = datetime.now()
print(now)  

# Formatting
print(now.strftime("%Y-%m-%d %H:%M:%S"))  
print(now.strftime("%A, %B %d, %Y"))      

# Adding days
future = now + timedelta(days=7)
print("After 7 days:", future)
```

---

## 6️⃣ Exercises

### 🔹 Exercise 1

Write a program that prints today’s date and time in the format:  
`DD-MM-YYYY HH:MM:SS`

### 🔹 Exercise 2

Use `random` to generate **lottery numbers** (6 unique numbers between 1 and 49).

### 🔹 Exercise 3

Simulate rolling a dice until you get a 6. Print the number of rolls it took.

```python
import random

rolls = 0
while True:
    rolls += 1
    dice = random.randint(1, 6)
    print(f"Rolled: {dice}")
    if dice == 6:
        print(f"Took {rolls} rolls to get a 6!")
        break
```

---

✅ By the end of Day 16 → You’ll understand **how to import modules, use `math`, `random`, `datetime`, and solve small real-world problems**.

---
