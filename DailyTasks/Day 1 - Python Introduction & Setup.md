
---

# 🗓️ Day 1 – Python Introduction & Setup

---

## 1️⃣ What is Python?

- Python is a **high-level, interpreted, object-oriented** programming language.
    
- Known for being **easy to learn**, **readable**, and **powerful**.
    
- Created by **Guido van Rossum** in **1991**.
    
- Used in:
    
    - **Web Development** (Django, Flask)
        
    - **Data Science & AI** (Pandas, NumPy, Scikit-learn, TensorFlow, PyTorch)
        
    - **Automation/Scripting**
        
    - **Game Development** (Pygame)
        
    - **DevOps, APIs, Cloud, IoT**
        

---

## 2️⃣ Features of Python

- **Simple & Readable** → Syntax close to English
    
- **Interpreted** → No compilation required
    
- **Dynamically Typed** → No need to declare variable types
    
- **Portable & Cross-platform** → Runs on Windows, Mac, Linux
    
- **Rich Standard Library** → Pre-built modules for almost everything
    
- **Supports OOP & Functional Programming**
    
- **Huge Community Support**
    

---

## 3️⃣ Python Installation & Setup

### 🔹 Install Python

- Download from [python.org](https://www.python.org/downloads/)
    
- On Linux/macOS → already pre-installed (`python3 --version`)
    
- Check version:
    
    ```bash
    python3 --version
    ```
    

### 🔹 Install an IDE/Editor

- Options:
    
    - **PyCharm** (Professional IDE)
        
    - **VS Code** (Lightweight, versatile)
        
    - **Jupyter Notebook** (For data science)
        
- For beginners → **VS Code + Python extension** is good.
    

---

## 4️⃣ Your First Python Program

### `hello.py`

```python
# This is a comment
print("Hello, World!")  # Output: Hello, World!
```

👉 Run in terminal:

```bash
python3 hello.py
```

Or run in interactive mode:

```bash
python3
>>> print("Hello, Python!")
```

---

## 5️⃣ Python Interpreter & REPL

- **REPL** → Read, Evaluate, Print, Loop
    
- Run by typing `python3` in terminal
    
- Example:
    
    ```python
    >>> 2 + 3
    5
    >>> "Python".upper()
    'PYTHON'
    ```
    

---

## 6️⃣ Comments in Python

- **Single-line comment** → starts with `#`
    
- **Multi-line comment** → use triple quotes `''' ... '''` or `""" ... """`
    

Example:

```python
# This is a single-line comment

"""
This is a
multi-line
comment
"""
```

---

## 7️⃣ Variables & Data Types (Quick Intro)

- No need to declare type explicitly.
    
- Python decides type dynamically.
    

```python
x = 10        # int
y = 3.14      # float
name = "Alice"  # string
is_active = True  # boolean
```

Use `type()` function:

```python
print(type(x))  # <class 'int'>
print(type(name))  # <class 'str'>
```

---

## 8️⃣ Basic Input & Output

```python
# Output
print("Welcome to Python!")

# Input
name = input("Enter your name: ")
print("Hello,", name)
```

---

## 9️⃣ Python Indentation

- Python **does not use `{}` brackets** for blocks.
    
- Uses **indentation (spaces/tabs)**.
    
- Standard → 4 spaces.
    

```python
if True:
    print("This is indented correctly")
```

---

## 🔟 Day 1 Exercises

1. Install Python & check version.
    
2. Print your name, age, and favorite hobby using `print()`.
    
3. Write a script that takes **two numbers** as input and prints their sum.
    
4. Try using comments to explain your code.
    
5. Open REPL and try:
    
    - `10 / 3`, `10 // 3`, `10 % 3`
        
    - `"python" * 3`
        
    - `"hello".capitalize()`
        

---

✅ By end of Day 1 → You can install Python, run scripts, use comments, take input/output, and understand variables & indentation.

---
