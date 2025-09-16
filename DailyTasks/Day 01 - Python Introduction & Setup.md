
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

Why IDE?
* Linting
* Debugging
* Autocomplete
* Code Formatting (PEP8)

Install Either Anaconda or Miniconda

Create Environment:
### Create a new environment with a specific Python version

conda create -n myenv python=3.11

#### Activate the environment
conda activate myenv

#### Install a package
conda install numpy

#### List environments
conda env list


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
    >>> 	2 + 3
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
    
- Python decides type dynamically. (Dynamic in nature)
    

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

```markdown
* Variable names can only contain letters, numbers and underscores
* Variable name can't start with a number
* Variable name can't contain spaces
* Variable name can't be same as python keywords like for, if, and etc
```

### Naming Convention

* Camel Case : CamelVariableName
* Pascal Case (Upper Camel Case): PascalVariableName
* Snake Case: snake_variable_name (Recommended)


If 2 variables have same name then it is actually reassigning the new value to the variable

#### Multiple Assignments

```python
var_a, var_b = "Hey", 1234 
var_a, var_b = var_b, var_a # Swap variables
```

Some of the variable types are:
```python
x = 10 # integer
x = 10.2 # float
x = "Hello" # String
x = [1,2,3] # List
x = (1,2,"a") # Tuple
x = {"a": 1, "b": "c"} # Dictionary (Dict)
x = {"a", "b", "c"} # Set 
```

String can be converted to int, Float
String --> List

In Python, **null** value is declared as **None**


---

## Mutable vs Immutable in Python

## Immutable objects

- **Definition**: Once created, they **cannot be changed** in place.
    
- Examples:
    
    - Numbers (`int`, `float`, `complex`)
        
    - Strings (`str`)
        
    - Tuples (`tuple`)
        
    - Frozen sets (`frozenset`)
        
    - Booleans (`True/False`)
        

```python
x = "hello"
print(id(x))      # memory address
x += " world"     # creates a NEW string
print(id(x))      # different address
```

👉 `"hello"` didn’t change; instead `"hello world"` was created.

---

## Mutable objects

- **Definition**: They **can be changed in place** without creating a new object.
    
- Examples:
    
    - Lists (`list`)
        
    - Dictionaries (`dict`)
        
    - Sets (`set`)
        
    - User-defined objects (by default)
        

```python
lst = [1, 2, 3]
print(id(lst))      # memory address
lst.append(4)       # modifies in place
print(id(lst))      # same address
```

👉 The list was modified, not recreated.

---

# 🔹 Why it matters

### 1. Function arguments

Mutable objects can be **changed inside functions**, immutables cannot.

```python
def modify_list(a):
    a.append(100)

def modify_number(x):
    x += 10

lst = [1, 2]
num = 5

modify_list(lst)
modify_number(num)

print(lst)  # [1, 2, 100] ✅ changed
print(num)  # 5 ❌ unchanged
```

---

### 2. Performance & memory

- Immutable objects are **hashable**, so they can be used as dictionary keys or set elements.
    
- Mutables usually cannot (lists, dicts).
    

```python
d = { (1, 2): "ok" }   # tuple works (immutable)
# d = { [1, 2]: "fail" }  # ❌ error: list is unhashable
```

---

### 3. Bugs

Sharing mutable objects between variables can cause **unexpected side effects**.

```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)  # [1, 2, 3, 4] 😱 a changed too
```

If you want a copy:

```python
b = a[:]    # shallow copy
```

---

# 🔹 Quick Comparison

| Feature                       | Mutable (list, dict, set) | Immutable (int, str, tuple) |
| ----------------------------- | ------------------------- | --------------------------- |
| Can modify in place           | ✅ Yes                     | ❌ No                        |
| Same object ID after change   | ✅ Yes                     | ❌ No (new object created)   |
| Hashable (usable as dict key) | ❌ Usually no              | ✅ Yes                       |
| Example                       | `[1, 2] → [1, 2, 3]`      | `"hi" → "hi there"`         |

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


## Types of Errors

---


# 🔹 1. **Syntax Errors**

- Happen when you **break the grammar rules** of Python.
    
- Python **won’t even run** your code.
    
- Detected **before execution** by the Python parser.
    

✅ Example:

```python
print("Hello"  # Missing closing parenthesis
```

Output:

```
SyntaxError: unexpected EOF while parsing
```

---

# 🔹 2. **Runtime Errors (Exceptions)**

- Code is **syntactically valid**, but something goes wrong **while running**.
    
- Python raises an **exception** at runtime.
    
- Common examples: division by zero, accessing missing files, wrong data type.
    

✅ Example:

```python
x = 10 / 0   # Division by zero at runtime
```

Output:

```
ZeroDivisionError: division by zero
```

---

# 🔹 3. **Logical Errors**

- Code **runs without crashing**, but the **result is wrong**.
    
- Hardest to detect because Python doesn’t warn you — only your output is incorrect.
    
- Happens due to a mistake in your **algorithm or logic**.
    

✅ Example:

```python
# Suppose you want the average of 3 numbers
nums = [10, 20, 30]
avg = sum(nums) / 2   # ❌ wrong denominator
print(avg)
```

Output:

```
30.0
```

Expected result was `20.0`. The program runs fine, but logic is incorrect.

---

# 🔹 Quick Summary

|Type of Error|When it Happens|Example|Python Reaction|
|---|---|---|---|
|**Syntax Error**|Before running|`print("hi`|Fails immediately|
|**Runtime Error**|During running|`10/0`|Raises exception|
|**Logical Error**|After running|Wrong avg formula|Wrong output|

---

# 🔹 What are comments?

- Comments are **notes in your code** that Python ignores during execution.
    
- Used to explain logic, mark TODOs, or make code easier to read.
    
- Python has **single-line** and **multi-line (docstring style)** comments.
    

---

# 🔹 1. Single-line Comments

Use the **hash symbol (`#`)**:

```python
# This is a single-line comment
x = 10  # Inline comment after code
```

Python ignores everything after `#` on that line.

---

# 🔹 2. Multi-line Comments

Python doesn’t have a special multi-line comment symbol like `/* ... */` in C,  
but you can:

### Option A: Use `#` on multiple lines

```python
# This is a multi-line comment
# explaining the next block of code
# in detail.
```

### Option B: Use Triple-quoted Strings (`""" ... """` or `''' ... '''`)

These are actually **strings**, but if they’re not assigned to a variable, Python just ignores them. Commonly used for docstrings:

```python
"""
This is also a comment style.
Often used for documentation
or temporarily disabling code.
"""
```

---

# 🔹 3. Docstrings (Special Comments for Functions/Classes)

Triple-quoted strings placed at the beginning of a **function, class, or module** are treated as **documentation** (not ignored completely — tools like `help()` or IDEs can read them).

Example:

```python
def add(a, b):
    """
    This function adds two numbers.
    Args:
        a (int): first number
        b (int): second number
    Returns:
        int: sum of a and b
    """
    return a + b

print(help(add))  # Shows the docstring
```

---

# 🔹 4. Best Practices for Comments

✅ Use comments to explain **why**, not just **what**.  
✅ Keep comments updated — outdated comments are worse than none.  
✅ Use docstrings for functions, classes, and modules.  
✅ For TODOs and FIXMEs, follow conventions:

```python
# TODO: optimize this loop
# FIXME: handle empty list case
```

---

# 🔹 Quick Summary

- `#` → single-line comment
    
- `""" ... """` → multi-line or docstring
    
- **Docstrings** → official documentation for functions/classes
    

---

# 🔹 Interpreted Programming Language

## ✅ Definition

An **interpreted language** is a type of programming language where the code is **executed line by line** (or statement by statement) by an **interpreter**, rather than being compiled into machine code beforehand.

That means:

- You write code → run it directly.
    
- No separate "compilation" step needed (though some interpreters may internally optimize).
    

---

## 🔹 Examples

- **Python**
    
- **JavaScript**
    
- **Ruby**
    
- **PHP**
    
- **Perl**
    

---

## 🔹 How it works

1. You write the source code (`.py`, `.js`, etc.).
    
2. The **interpreter** reads it line by line, translates into lower-level instructions, and executes immediately.
    

For example in Python:

```python
print("Hello")
x = 5 + 2
print(x)
```

The Python interpreter will:

1. Print `"Hello"`
    
2. Calculate `5+2`
    
3. Print `7`
    

All while **running sequentially**.

---

## 🔹 Difference vs Compiled Language

|Feature|Interpreted|Compiled|
|---|---|---|
|Execution|Line by line (at runtime)|Translated fully into machine code before execution|
|Speed|Slower (extra translation at runtime)|Faster (already machine code)|
|Portability|Very portable (just need interpreter)|Platform-specific executables|
|Examples|Python, JS, Ruby|C, C++, Rust, Go|

---

## 🔹 Hybrid cases

Some languages **mix both**:

- **Java** → compiled to bytecode, then interpreted (JVM).
    
- **Python** → actually compiles to _bytecode_ (`.pyc`) first, then interprets.
    
- **JavaScript** in browsers → interpreted, but modern engines (V8) also use **JIT compilation** for speed.
    

---

✅ So, **interpreted language = you don’t need to compile before running, the interpreter handles execution dynamically**.

---

# 🔹 Normal Python Execution

When you run:

```bash
python script.py
```

Python does:

1. **Parses** your source code.
    
2. **Compiles** it into **bytecode** (`.pyc` files in `__pycache__`).
    
3. Runs the bytecode in the **Python Virtual Machine (PVM)**.
    

So technically, Python is already "compiled" — but into bytecode, not machine code.

---

# 🔹 Ahead-of-Time (AOT) Compilation Options

### 1. **Bytecode compilation**

You can precompile `.py` into `.pyc`:

```bash
python -m compileall your_script.py
```

This creates a `.pyc` file in `__pycache__`.  
Later, you can just run the `.pyc` without recompiling.

But ⚠️: It’s still bytecode, needs Python interpreter.

---

### 2. **Cython (Python → C → Machine Code)**

[Cython](https://cython.org/) lets you compile Python (optionally with type hints) into **C extensions**, then build machine code binaries.

Example:

```bash
cython --embed -o script.c script.py
gcc -o script script.c $(python3-config --cflags --ldflags)
```

Now you can run `./script` directly without Python source.  
✅ Faster, real native executable.

---

### 3. **Nuitka**

[Nuitka](https://nuitka.net/) is a full Python **AOT compiler**. It converts Python into C++ and then into a binary executable.

```bash
nuitka --standalone --onefile script.py
```

Now you have a single `.exe` (Windows) or binary (Linux).

✅ Preserves full Python compatibility.  
✅ Can distribute without `.py` files.

---

### 4. **PyInstaller / cx_Freeze / py2exe**

These don’t actually compile to machine code, but **bundle** your Python interpreter + bytecode into a single binary:

```bash
pyinstaller --onefile script.py
```

You get `dist/script` (executable).

✅ Easy packaging.  
⚠️ File size is big (since Python interpreter is included).

---

### 5. **JIT alternatives (not pure AOT)**

- **PyPy** → uses **Just-In-Time compilation** for speed at runtime.
    
- **Numba** → JIT-compiles numeric Python code to machine code using LLVM.
    

---

# 🔹 Which one to use?

- If you want **faster execution** → use **Cython, Numba, or Nuitka**.
    
- If you want **distribution without source** → use **PyInstaller / Nuitka**.
    
- If you want **just precompiled bytecode** → use `compileall`.
    

---
