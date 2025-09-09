
---


By now, you have covered:

- **Functions, arguments, lambda, decorators**
    
- **Modules and standard utilities** (`math`, `random`, `datetime`)
    
- **Advanced data structures** (`collections`)
    
- **Functional programming helpers** (`functools`)
    
- **Iteration utilities** (`itertools`)
    
- **OS and system interaction** (`os`, `sys`)
    
- **Regular expressions** (`re`)
    
- **Creating your own modules and packages**
    

Today, we **combine everything** into a real-world mini project.

---

## 1️⃣ Mini Project Ideas

### 🔹 1. Log Analyzer

**Goal:** Analyze `.log` files and find frequent IP addresses.

```python
import os
import re
from collections import Counter

log_folder = "logs"

all_ips = []

# Read all .log files
for filename in os.listdir(log_folder):
    if filename.endswith(".log"):
        with open(os.path.join(log_folder, filename)) as f:
            for line in f:
                # Extract IPs using regex
                ips = re.findall(r"\b(?:[0-9]{1,3}\.){3}[0-9]{1,3}\b", line)
                all_ips.extend(ips)

# Count most common IPs
ip_counts = Counter(all_ips)
print("Top 5 IPs:", ip_counts.most_common(5))
```

**Concepts Used:** `os`, `re`, `collections.Counter`, loops

---

### 🔹 2. Password Generator

**Goal:** Generate strong passwords with user-defined rules.

```python
import random
import string

def generate_password(length=12, use_upper=True, use_digits=True, use_symbols=True):
    chars = string.ascii_lowercase
    if use_upper:
        chars += string.ascii_uppercase
    if use_digits:
        chars += string.digits
    if use_symbols:
        chars += string.punctuation
    
    return ''.join(random.choice(chars) for _ in range(length))

print("Generated Password:", generate_password(16))
```

**Concepts Used:** `random`, `string`, functions, arguments

---

### 🔹 3. Student Report

**Goal:** Read CSV file of students, calculate totals, rank them.

```python
import csv
from functools import reduce

# Sample CSV: name,math,science,english
students = []

with open("students.csv") as f:
    reader = csv.DictReader(f)
    for row in reader:
        total = reduce(lambda x, y: x + y, [int(row["math"]), int(row["science"]), int(row["english"])])
        students.append({"name": row["name"], "total": total})

# Rank students by total
students_sorted = sorted(students, key=lambda x: x["total"], reverse=True)

print("Student Rankings:")
for s in students_sorted:
    print(f"{s['name']}: {s['total']}")
```

**Concepts Used:** `csv`, `functools.reduce`, `lambda`, `sorted`

---

## 2️⃣ Key Takeaways

- Combine **multiple modules** for real-world problems.
    
- Modular code and proper **function design** make projects scalable.
    
- Use **data structures and utilities** efficiently (`Counter`, `reduce`, `sorted`).
    
- Regular expressions and OS interaction are extremely useful for **text/file processing**.
    

---

By completing **Day 23**, you now have **hands-on experience integrating modules and Python utilities** to solve practical problems.

---
