When you write functions, variables can **exist in different scopes** (regions of code where they are accessible).  
Python follows the **LEGB Rule**:

- **L** → Local (inside function)
    
- **E** → Enclosing (in nested functions)
    
- **G** → Global (top-level in script)
    
- **B** → Built-in (Python’s built-in names like `len`, `print`)
    

---

## 1️⃣ Local Scope

- Variables declared inside a function → **local** to that function.
    

```python
def my_function():
    x = 10  # local
    print("Inside function:", x)

my_function()
# print(x)   # ❌ Error: x not defined outside
```

---

## 2️⃣ Global Scope

- Variables declared at the **top-level** of a script/module.
    
- Accessible everywhere **inside functions (read-only)** unless explicitly modified.
    

```python
x = 20  # global

def show():
    print("Inside function:", x)  # Can access global

show()
print("Outside function:", x)
```

✅ Output:

```
Inside function: 20
Outside function: 20
```

---

## 3️⃣ Modifying Global Variables → `global` Keyword

If you want to **modify a global variable inside a function**, use `global`.

```python
count = 0

def increment():
    global count
    count += 1
    print("Inside function:", count)

increment()
increment()
print("Outside function:", count)
```

✅ Output:

```
Inside function: 1
Inside function: 2
Outside function: 2
```

⚠️ Avoid overusing `global` → makes debugging harder. Prefer return values.

---

## 4️⃣ Enclosing Scope (Nested Functions)

- Variables defined in an **outer function** but used in an **inner function**.
    

```python
def outer():
    x = "outer variable"

    def inner():
        print("Accessing from inner:", x)  # enclosing scope

    inner()

outer()
```

✅ Output:

```
Accessing from inner: outer variable
```

---

## 5️⃣ `nonlocal` Keyword

- Used in **nested functions** to modify a variable from the **enclosing (non-global) scope**.
    

```python
def outer():
    x = 0

    def inner():
        nonlocal x
        x += 1
        print("Inner:", x)

    inner()
    inner()
    print("Outer:", x)

outer()
```

✅ Output:

```
Inner: 1
Inner: 2
Outer: 2
```

---

## 6️⃣ LEGB Rule in Action

```python
x = "global"

def outer():
    x = "enclosing"

    def inner():
        x = "local"
        print("Inner:", x)

    inner()
    print("Outer:", x)

outer()
print("Global:", x)
```

✅ Output:

```
Inner: local
Outer: enclosing
Global: global
```

---

## 7️⃣ Best Practices

- Minimize use of `global` → prefer returning values.
    
- Use `nonlocal` only when closures/decorators need state tracking.
    
- Always remember **LEGB Rule** when debugging variable scope issues.
    

---

## 8️⃣ Exercises

1. Write a function with a **local variable** and try accessing it outside (see error).
    
2. Create a function that increments a **global counter** using `global`.
    
3. Build a **nested function** where the inner function uses an enclosing variable.
    
4. Modify enclosing variable with `nonlocal`.
    
5. Write a program to demonstrate **LEGB Rule** (local → enclosing → global).
    

---

✅ By end of Day 11 → You’ll clearly understand **variable lifetimes and scopes**, and when to use `global` vs `nonlocal`.

---
