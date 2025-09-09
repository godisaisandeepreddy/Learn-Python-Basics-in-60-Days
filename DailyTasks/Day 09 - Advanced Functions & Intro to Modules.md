Functions become powerful when we pass **data as input**.  
Python offers several ways to pass parameters: **positional, keyword, and default arguments**.

---

## 1️⃣ Positional Parameters

- Arguments are passed **in the same order** as defined in the function.
    

```python
def greet(name, age):
    print(f"Hello {name}, you are {age} years old.")

greet("Alice", 25)   # Hello Alice, you are 25 years old.
```

⚠️ If you miss a required argument, Python throws an error.

```python
greet("Bob")   # ❌ TypeError: missing required argument
```

---

## 2️⃣ Default Parameters

- You can **assign default values** so arguments become optional.
    

```python
def greet(name="Guest", age=18):
    print(f"Hello {name}, you are {age} years old.")

greet()                 # Hello Guest, you are 18 years old.
greet("Alice")          # Hello Alice, you are 18 years old.
greet("Bob", 30)        # Hello Bob, you are 30 years old.
```

✅ Useful when some parameters usually have a common value.

---

## 3️⃣ Keyword Arguments

- You can pass arguments by **name**, not just position.
    

```python
def student_info(name, grade, city):
    print(f"Name: {name}, Grade: {grade}, City: {city}")

student_info("Alice", "A", "London")            # positional
student_info(name="Bob", grade="B", city="NY")  # keyword
student_info(grade="A", city="Delhi", name="Eva")  # order doesn’t matter
```

⚠️ But **positional must come before keyword**:

```python
student_info("Alice", grade="A", city="Paris")   # ✅ works
student_info(name="Alice", "A", "Paris")        # ❌ Error
```

---

## 4️⃣ Mixing Positional & Keyword Arguments

- You can combine them, but **positional first**.
    

```python
def power(base, exponent):
    return base ** exponent

print(power(2, 3))          # 8
print(power(base=2, exponent=5))   # 32
print(power(3, exponent=2))        # 9
```

---

## 5️⃣ Best Practices

- Use **positional** for required inputs.
    
- Use **default** for optional values.
    
- Use **keyword** for clarity in function calls.
    

Example:

```python
def book_ticket(name, seat_type="Economy", meal="Veg"):
    print(f"Passenger: {name}, Seat: {seat_type}, Meal: {meal}")

book_ticket("John")  
book_ticket("Alice", "Business")  
book_ticket(name="Bob", meal="Non-Veg")  
```

---

## 6️⃣ Exercises

1. Write a function `full_name(first, last)` that prints `"Hello First Last"`.
    
2. Add a default argument `greeting="Hello"` to `full_name`. Example:
    
    ```python
    full_name("Alice", "Smith")        # Hello Alice Smith
    full_name("Bob", "Brown", "Hi")    # Hi Bob Brown
    ```
    
3. Write a function `student(name, grade="A", city="Unknown")` and test different combinations of parameters.
    
4. Write a function `rectangle_area(length, width)` and call it using:
    
    - positional arguments
        
    - keyword arguments
        
    - mix of both
        
5. Try calling a function with a missing required argument to see the error.
    

---

✅ By end of Day 9 → You’ll know how to pass **positional, default, and keyword parameters** effectively.

---
