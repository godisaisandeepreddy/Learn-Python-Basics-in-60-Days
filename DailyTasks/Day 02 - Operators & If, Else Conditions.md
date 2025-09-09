
---

## 1️⃣ Python Operators

Operators are symbols that perform operations on values or variables.

### 🔹 Arithmetic Operators

```python
a = 10
b = 3

print(a + b)  # 13 (Addition)
print(a - b)  # 7  (Subtraction)
print(a * b)  # 30 (Multiplication)
print(a / b)  # 3.333... (Division, float)
print(a // b) # 3 (Floor division)
print(a % b)  # 1 (Modulus)
print(a ** b) # 1000 (Exponentiation)
```

---

### 🔹 Comparison (Relational) Operators

```python
x = 5
y = 10

print(x == y)  # False (equal)
print(x != y)  # True  (not equal)
print(x > y)   # False
print(x < y)   # True
print(x >= y)  # False
print(x <= y)  # True
```

---

### 🔹 Logical Operators

```python
a = True
b = False

print(a and b)  # False
print(a or b)   # True
print(not a)    # False
```

---

### 🔹 Assignment Operators

```python
num = 10
num += 5   # num = num + 5 → 15
num -= 3   # num = num - 3 → 12
num *= 2   # num = num * 2 → 24
num /= 4   # num = num / 4 → 6.0
```

---

### 🔹 Identity Operators

```python
x = [1, 2, 3]
y = x
z = [1, 2, 3]

print(x is y)   # True (same memory reference)
print(x is z)   # False (different objects)
print(x is not z) # True
```

---

### 🔹 Membership Operators

```python
nums = [1, 2, 3, 4, 5]

print(3 in nums)    # True
print(6 not in nums) # True
```

---

## 2️⃣ Control Structures – If/Else

Python controls execution flow with conditions.

### 🔹 If Statement

```python
age = 18

if age >= 18:
    print("You are eligible to vote")
```

---

### 🔹 If-Else

```python
x = 5

if x % 2 == 0:
    print("Even number")
else:
    print("Odd number")
```

---

### 🔹 If-Elif-Else

```python
marks = 85

if marks >= 90:
    print("Grade: A")
elif marks >= 75:
    print("Grade: B")
elif marks >= 50:
    print("Grade: C")
else:
    print("Grade: Fail")
```

---

### 🔹 Nested If

```python
num = 15

if num > 0:
    if num % 2 == 0:
        print("Positive even number")
    else:
        print("Positive odd number")
else:
    print("Non-positive number")
```

---

## 3️⃣ Short-hand If (Ternary Operator)

```python
x = 10
result = "Even" if x % 2 == 0 else "Odd"
print(result)  # Even
```

---

## 4️⃣ Day 2 Exercises

1. Take a number from the user and check if it’s **positive, negative, or zero**.
    
2. Take a number and check if it’s **even or odd**.
    
3. Write a program that asks age and prints:
    
    - `"Child"` if age < 13
        
    - `"Teenager"` if 13–19
        
    - `"Adult"` if 20–59
        
    - `"Senior Citizen"` if 60+
        
4. Use membership operator to check if `"apple"` is in `["banana", "apple", "cherry"]`.
    
5. Use identity operator to check difference between:
    
    ```python
    a = [1, 2, 3]
    b = [1, 2, 3]
    print(a is b)
    print(a == b)
    ```
    

---

✅ By end of Day 2 → You will master **operators** and **if/else decision making** in Python.

---
