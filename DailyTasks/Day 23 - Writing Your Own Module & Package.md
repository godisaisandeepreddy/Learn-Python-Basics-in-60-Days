
Creating **modules and packages** helps organize Python code and **reuse it across projects**.

---

## 1️⃣ What is a Module?

- A **module** is a single Python file containing **functions, classes, or variables**.
    
- Any `.py` file is a module.
    

### 🔹 Example: `mymath.py`

```python
# mymath.py

def add(a, b):
    return a + b

def sub(a, b):
    return a - b
```

---

## 2️⃣ Importing a Module

- Use `import <module_name>` to access functions.
    

```python
# main.py
import mymath

print(mymath.add(5, 3))   # 8
print(mymath.sub(10, 4))  # 6
```

### 🔹 Import specific functions

```python
from mymath import add, sub

print(add(7, 2))  # 9
```

---

## 3️⃣ What is a Package?

- A **package** is a folder containing **modules** and an optional `__init__.py` file.
    
- Allows grouping **related modules** together.
    

### 🔹 Example Folder Structure

```
mypackage/
    __init__.py
    module1.py
    module2.py
```

- `__init__.py` can be empty or initialize the package.
    

### 🔹 Importing from Package

```python
from mypackage import module1
from mypackage.module2 import some_function
```

---

## 4️⃣ `__name__ == "__main__"`

- Ensures code **only runs when the file is executed directly**, not when imported.
    

```python
# mymath.py
def add(a, b):
    return a + b

if __name__ == "__main__":
    print("Testing add function:", add(5, 3))
```

- Run `python mymath.py` → prints test output.
    
- Import in another file → no output, only functions are available.
    

---

## 5️⃣ Exercise: Create a `geometry` Package

1. **Folder structure:**
    

```
geometry/
    __init__.py
    circle.py
    rectangle.py
```

2. **circle.py**
    

```python
import math

def area(radius):
    return math.pi * radius**2

def perimeter(radius):
    return 2 * math.pi * radius
```

3. **rectangle.py**
    

```python
def area(length, width):
    return length * width

def perimeter(length, width):
    return 2 * (length + width)
```

4. **Using the package**
    

```python
from geometry import circle, rectangle

print("Circle area:", circle.area(5))
print("Circle perimeter:", circle.perimeter(5))

print("Rectangle area:", rectangle.area(4, 6))
print("Rectangle perimeter:", rectangle.perimeter(4, 6))
```

✅ Output:

```
Circle area: 78.53981633974483
Circle perimeter: 31.41592653589793
Rectangle area: 24
Rectangle perimeter: 20
```

---

### 6️⃣ Notes

- Packages help **keep code organized**, especially for large projects.
    
- Modules/packages **can import each other** for modular code.
    
- Always use `__name__ == "__main__"` for **testing or scripts**.
    

---
