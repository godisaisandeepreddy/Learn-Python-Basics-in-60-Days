
---

## Concept: Comprehensions — why & when

Comprehensions provide a compact, readable way to build new collections from iterables.

- **List comprehension** — build lists.
    
- **Dict comprehension** — build dictionaries.
    
- **Set comprehension** — build sets.
    
- **Generator expression** — like list comp but lazy (use `()`), memory-friendly.
    

They’re often faster and shorter than equivalent `for` loops, but avoid overcomplicating — if comprehension becomes unreadable, use plain loops.

---

## Syntax & examples

### List comprehension

Equivalent:

```python
# loop form
squares = []
for x in range(10):
    squares.append(x**2)

# comprehension form
squares = [x**2 for x in range(10)]
```

### Dict comprehension

```python
# {key: value for item in iterable if condition}
square_map = {x: x**2 for x in range(5)}  # {0:0,1:1,2:4,3:9,4:16}
```

### Set comprehension

```python
chars = {c for c in "banana"}  # {'b', 'n', 'a'}
```

### Conditional comprehensions

```python
evens = [x for x in range(20) if x % 2 == 0]
```

### Nested comprehensions

Flattening a matrix:

```python
matrix = [[1,2,3],[4,5,6],[7,8,9]]
flat = [num for row in matrix for num in row]  # [1,2,3,4,5,6,7,8,9]
# note: order is 'for row in matrix' then 'for num in row'
```

### Generator expression (lazy)

```python
gen = (x**2 for x in range(10))  # uses less memory
for v in gen:
    print(v)
```

---

## Short pitfalls / tips

- Comprehensions should be simple. If you need many nested loops + conditionals, consider a normal loop for readability.
    
- Use generator expressions when working with large data to save memory.
    
- When building complex dictionaries, ensure keys are unique (dict comprehension will overwrite duplicates).
    

---

## Day 7 Exercises

1. Create a list of squares for even numbers from 0–20 using list comprehension.
    
2. Using dict comprehension, transform `["a","b","c"]` into `{'a':1, 'b':2, 'c':3}`.
    
3. Flatten `[[1,2],[3,4],[5,6]]` using a nested comprehension.
    
4. Create a set of unique words lengths from `"one two three three"`.
    
5. Convert this loop to comprehension:
    
    ```python
    result = []
    for i in range(5):
        for j in range(3):
            result.append((i, j))
    ```
    
6. Write a generator expression that yields the first 100 primes (hint: use a helper prime-check function and `if` inside comprehension).
    

---

## Mini Projects — choose one

### 1) Student Grade System (complete sample)

**Requirements**

- Input: list of students and list of marks (or read from CSV).
    
- Compute average and assign grade:
    
    - `A` if avg >= 90
        
    - `B` if avg >= 75
        
    - `C` if avg >= 50
        
    - `Fail` otherwise
        
- Store results in a `dict` like `{"Alice": {"avg": 87.5, "grade": "B"}}`.
    

**Sample implementation**

```python
# student_grade_system.py
def assign_grade(avg):
    if avg >= 90:
        return "A"
    elif avg >= 75:
        return "B"
    elif avg >= 50:
        return "C"
    else:
        return "Fail"

def compute_results(student_marks):
    # student_marks: {"Alice":[90,85], "Bob":[70,65]}
    results = {name: {"avg": sum(marks)/len(marks), "grade": None}
               for name, marks in student_marks.items()}
    for name, info in results.items():
        info["grade"] = assign_grade(info["avg"])
    return results

if __name__ == "__main__":
    data = {
        "Alice": [95, 85, 92],
        "Bob": [70, 60, 65],
        "Charlie": [50, 55, 53]
    }
    res = compute_results(data)
    for name, info in res.items():
        print(f"{name}: avg={info['avg']:.2f}, grade={info['grade']}")
```

**Extensions**

- Read input from CSV, export results to CSV.
    
- Add median, highest/lowest subject, or class average.
    

---

### 2) ATM Simulation (complete sample)

**Requirements**

- Maintain a balance.
    
- Menu: deposit, withdraw, check balance, quit.
    
- Use loops and conditionals; validate inputs.
    

**Sample implementation**

```python
# atm_sim.py
def show_menu():
    print("\n--- ATM Menu ---")
    print("1. Check balance")
    print("2. Deposit")
    print("3. Withdraw")
    print("4. Exit")

def atm():
    balance = 1000.0  # starting balance
    while True:
        show_menu()
        choice = input("Choose option: ").strip()
        if choice == "1":
            print(f"Current balance: ₹{balance:.2f}")
        elif choice == "2":
            amt = float(input("Deposit amount: "))
            if amt > 0:
                balance += amt
                print(f"Deposited ₹{amt:.2f}")
            else:
                print("Enter positive amount.")
        elif choice == "3":
            amt = float(input("Withdraw amount: "))
            if 0 < amt <= balance:
                balance -= amt
                print(f"Withdrawn ₹{amt:.2f}")
            else:
                print("Invalid amount or insufficient funds.")
        elif choice == "4":
            print("Thank you! Goodbye.")
            break
        else:
            print("Invalid option. Try again.")

if __name__ == "__main__":
    atm()
```

**Extensions**

- Add PIN authentication.
    
- Maintain transaction history with timestamps.
    
- Simulate multiple accounts (dict keyed by account no).
    

---
