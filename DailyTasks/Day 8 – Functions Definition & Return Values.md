
---

## 1️⃣ What is a Function?

- A **function** is a block of organized, reusable code that performs a single action.
    
- Helps in:
    
    - **Code reusability**
        
    - **Avoiding repetition**
        
    - **Better readability & debugging**
        

### 🔹 Defining a Function

```python
def greet():
    print("Hello, welcome to Python!")
```

### 🔹 Calling a Function

```python
greet()
```

---

## 2️⃣ Returning Values

- A function can **return data** using the `return` statement.
    

```python
def add(a, b):
    return a + b

result = add(5, 7)
print(result)  # 12
```

- If no `return` is used, the function returns `None`.
    

```python
def say_hello():
    print("Hello!")

output = say_hello()   # prints "Hello!"
print(output)          # None
```

---

## 3️⃣ Multiple Return Values

Python allows returning **multiple values** as a **tuple**.

```python
def calc(a, b):
    return a + b, a - b, a * b

s, d, m = calc(10, 5)
print(s, d, m)  # 15 5 50
```

---

## 4️⃣ Best Practices for Functions

- Use **meaningful names** (`calculate_area` vs `func1`).
    
- Functions should **do one task only**.
    
- Keep them short and modular.
    
- Add **docstrings** for clarity.
    

Example with docstring:

```python
def square(num):
    """
    Returns the square of a number.
    :param num: int or float
    :return: int or float
    """
    return num * num
```

---

## 5️⃣ Exercises

1. Write a function `welcome_message()` that prints `"Welcome to Python Learning!"`.
    
2. Write a function `multiply(x, y)` that returns the product of two numbers.
    
3. Write a function `cube(n)` that returns the cube of a number.
    
4. Write a function `operations(a, b)` that returns the sum, difference, product, and quotient.
    
5. Write a function `is_positive(num)` that returns `True` if a number is positive, otherwise `False`.
    
6. Try calling a function without `return` and observe what happens.
    

---

✅ By end of Day 8 → You’ll understand **function creation, calling, return values, and best practices**.

---

👉 Do you want me to now prepare **Day 9: Function Parameters (positional, default, keyword)** in the same detailed teaching material format?
---

## 1️⃣ What is a Function?

- A **function** is a block of reusable code that performs a specific task.
    
- Helps in **code reusability**, **modularity**, and **readability**.
    

### 🔹 Basic Function

```python
def greet():
    print("Hello, welcome to Python!")

greet()   # calling function
```

---

## 2️⃣ Function Parameters & Return Values

### 🔹 Parameters (Inputs)

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # Hello, Alice!
```

### 🔹 Multiple Parameters

```python
def add(a, b):
    return a + b

result = add(5, 7)
print(result)   # 12
```

### 🔹 Default Parameters

```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()        # Hello, Guest!
greet("Bob")   # Hello, Bob!
```

### 🔹 Keyword Arguments

```python
def student_info(name, age):
    print(f"Name: {name}, Age: {age}")

student_info(age=20, name="Alice")  # order doesn’t matter
```

### 🔹 Variable-Length Arguments

- **`*args`** → multiple positional arguments
    
- **`**kwargs`** → multiple keyword arguments
    

```python
def show_scores(*args):
    print("Scores:", args)

show_scores(80, 90, 70)  # Scores: (80, 90, 70)


def show_details(**kwargs):
    for key, value in kwargs.items():
        print(key, ":", value)

show_details(name="John", age=22, city="Delhi")
```

---

## 3️⃣ Scope of Variables

- **Local variable** → Defined inside a function, accessible only there.
    
- **Global variable** → Defined outside, accessible everywhere.
    

```python
x = 10  # global

def test():
    x = 5  # local
    print("Inside function:", x)

test()
print("Outside function:", x)
```

🔹 Use `global` keyword if you want to modify global variable inside a function:

```python
count = 0

def increment():
    global count
    count += 1

increment()
print(count)   # 1
```

---

## 4️⃣ Lambda Functions

- **Anonymous functions** defined with `lambda`.
    
- Useful for short, one-line functions.
    

```python
square = lambda x: x ** 2
print(square(5))   # 25
```

```python
add = lambda a, b: a + b
print(add(3, 7))   # 10
```

✅ **Use Case**: Often used with `map()`, `filter()`, and `sorted()`.

---

## 5️⃣ Built-in Functions with Functions

### 🔹 `map()` → Apply function to every element

```python
nums = [1, 2, 3, 4]
squares = list(map(lambda x: x**2, nums))
print(squares)   # [1, 4, 9, 16]
```

### 🔹 `filter()` → Filter items with condition

```python
nums = [10, 15, 20, 25, 30]
evens = list(filter(lambda x: x % 2 == 0, nums))
print(evens)   # [10, 20, 30]
```

### 🔹 `zip()` → Combine iterables

```python
names = ["Alice", "Bob", "Charlie"]
scores = [85, 92, 78]

combined = list(zip(names, scores))
print(combined)  # [('Alice', 85), ('Bob', 92), ('Charlie', 78)]
```

### 🔹 `enumerate()` → Get index with value

```python
fruits = ["apple", "banana", "cherry"]

for index, fruit in enumerate(fruits, start=1):
    print(index, fruit)
```

Output:

```
1 apple
2 banana
3 cherry
```

---

## 6️⃣ Day 7 Exercises

1. Write a function `multiply(a, b)` that returns the product.
    
2. Write a function `is_even(n)` that returns `True` if a number is even, else `False`.
    
3. Create a function `greet_user(name="Guest")` with a default argument.
    
4. Write a function `sum_all(*args)` that adds unlimited numbers.
    
5. Write a function `student(**kwargs)` that prints student info.
    
6. Use `lambda` and `map()` to convert `[2, 4, 6]` into their cubes `[8, 64, 216]`.
    
7. Use `filter()` to extract names longer than 4 characters from `["Tom", "Alice", "Bob", "Charlie"]`.
    
8. Use `zip()` to combine `["India", "USA", "UK"]` with `["Delhi", "Washington", "London"]`.
    
9. Write a program that uses `enumerate()` to print numbers with their squared values.
    

---

✅ By end of Day 7 → You’ll master **functions, arguments, scope, lambda, and powerful built-in functions for data processing**.

---
