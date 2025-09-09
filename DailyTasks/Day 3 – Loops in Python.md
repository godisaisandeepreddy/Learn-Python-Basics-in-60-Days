
---

## 1️⃣ Why Loops?

Loops let us **repeat a block of code multiple times** instead of writing it again and again.

Python has two main loops:

- `for` loop → iterates over a sequence (list, string, range, etc.)
    
- `while` loop → repeats until a condition becomes false
    

---

## 2️⃣ `for` Loop

### 🔹 Basic Syntax

```python
for variable in sequence:
    # code block
```

### 🔹 Examples

```python
# Loop through a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# Loop through a string
for char in "Python":
    print(char)

# Loop with range()
for i in range(5):
    print(i)   # 0, 1, 2, 3, 4

# Range with start & step
for i in range(2, 10, 2):
    print(i)   # 2, 4, 6, 8
```

---

## 3️⃣ `while` Loop

### 🔹 Basic Syntax

```python
while condition:
    # code block
```

### 🔹 Examples

```python
# Print numbers 1–5
i = 1
while i <= 5:
    print(i)
    i += 1

# Countdown
n = 5
while n > 0:
    print(n)
    n -= 1
print("Blast off!")
```

⚠️ Be careful with **infinite loops**:

```python
while True:
    print("Running forever... (Press Ctrl+C to stop)")
```

---

## 4️⃣ Loop Control Statements

### 🔹 `break` → exit the loop immediately

```python
for i in range(10):
    if i == 5:
        break
    print(i)   # stops at 4
```

---

### 🔹 `continue` → skip the current iteration

```python
for i in range(5):
    if i == 2:
        continue
    print(i)   # prints 0,1,3,4
```

---

### 🔹 `else` with loops → executes only if loop finishes without `break`

```python
for i in range(5):
    print(i)
else:
    print("Loop finished successfully")

# Example with break
for i in range(5):
    if i == 3:
        break
    print(i)
else:
    print("This will not run because of break")
```

---

## 5️⃣ Nested Loops

Loop inside another loop.

```python
for i in range(3):
    for j in range(2):
        print(f"i={i}, j={j}")
```

---

## 6️⃣ Day 3 Exercises

1. Print numbers from **1 to 10** using both `for` and `while` loop.
    
2. Write a program to print the **multiplication table of 7**.
    
3. Use a loop to **reverse a string** (without slicing).
    
4. Write a program that asks for a number `n` and prints all numbers from `n` down to `1`.
    
5. Print a pattern using nested loops:
    
    ```
    *
    **
    ***
    ****
    *****
    ```
    
6. Use `break` to stop when the loop reaches number 7 in range(1, 20).
    
7. Use `continue` to skip printing odd numbers from 1 to 10.
    
8. Write a loop with `else` that confirms loop completed successfully.
    

---

✅ By end of Day 3 → You will master **for loops, while loops, break, continue, else on loops, and nested loops**.

---
