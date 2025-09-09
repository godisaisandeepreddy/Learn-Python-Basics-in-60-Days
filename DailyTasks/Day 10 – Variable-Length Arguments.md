Sometimes we don’t know **how many arguments** a function will receive.  
Python solves this with **`*args` (positional)** and **`**kwargs` (keyword)**.

---

## 1️⃣ `*args` → Variable-Length Positional Arguments

- Collects **multiple positional arguments** into a **tuple**.
    

```python
def add_numbers(*args):
    print(args)        # tuple of all values
    return sum(args)

print(add_numbers(2, 4, 6))          # (2, 4, 6) → 12
print(add_numbers(5, 10, 15, 20))    # (5, 10, 15, 20) → 50
```

✅ Use Case: When you don’t know how many numbers (or items) will be passed.

---

## 2️⃣ `**kwargs` → Variable-Length Keyword Arguments

- Collects **multiple keyword arguments** into a **dictionary**.
    

```python
def show_info(**kwargs):
    print(kwargs)       # dictionary of key-value pairs
    for key, value in kwargs.items():
        print(f"{key}: {value}")

show_info(name="Alice", age=25, city="London")
```

Output:

```
{'name': 'Alice', 'age': 25, 'city': 'London'}
name: Alice
age: 25
city: London
```

✅ Use Case: Useful when passing flexible metadata (e.g., configs, user info).

---

## 3️⃣ Combining `*args` and `**kwargs`

- You can use both, but **order matters** → `positional → *args → default → **kwargs`.
    

```python
def details(course, *students, **info):
    print("Course:", course)
    print("Students:", students)
    print("Extra Info:", info)

details("Python", "Alice", "Bob", "Charlie", duration="3 months", level="Beginner")
```

Output:

```
Course: Python
Students: ('Alice', 'Bob', 'Charlie')
Extra Info: {'duration': '3 months', 'level': 'Beginner'}
```

---

## 4️⃣ Argument Unpacking

👉 You can unpack a list/tuple into `*args` and a dict into `**kwargs`.

```python
def greet(name, age, city):
    print(f"Hello {name}, age {age}, from {city}")

person = ("Alice", 25, "Paris")
greet(*person)   # unpack tuple

info = {"name": "Bob", "age": 30, "city": "London"}
greet(**info)    # unpack dictionary
```

---

## 5️⃣ Best Practices

- Use `*args` when function needs flexible **positional** inputs.
    
- Use `**kwargs` when function needs flexible **keyword** inputs.
    
- Keep functions clean: don’t overuse `*args`/`**kwargs` unless necessary.
    

---

## 6️⃣ Exercises

1. Write a function `multiply_all(*args)` that multiplies all numbers passed.  
    Example: `multiply_all(2, 3, 4)` → 24
    
2. Write a function `profile(**kwargs)` that prints user details.  
    Example:
    
    ```python
    profile(name="John", age=28, job="Engineer")
    ```
    
    Output:
    
    ```
    name: John
    age: 28
    job: Engineer
    ```
    
3. Create a function `order(food, *extras, **details)` and call it like:
    
    ```python
    order("Pizza", "Cheese", "Olives", size="Large", takeaway=True)
    ```
    
4. Use unpacking with a list `nums = [2, 4, 6]` to pass values into a function `sum(a, b, c)`.
    
5. Use unpacking with a dictionary `{"name": "Alice", "city": "Paris"}` in a function `introduce(name, city)`.
    

---

✅ By end of Day 10 → You’ll master **flexible functions with `*args` & `**kwargs`, argument unpacking, and practical use cases**.

---

👉 Shall I continue with **Day 11: Variable Scope (local, global, nonlocal)** in the same detailed step-by-step teaching format?