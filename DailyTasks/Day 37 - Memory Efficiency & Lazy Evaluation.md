When working with **large datasets or files**, memory becomes a bottleneck.  
Generators and lazy evaluation help you process data **without loading everything at once**.

---

## 1️⃣ Lists vs Generators Memory Usage

Lists store all elements in memory.  
Generators produce items **on demand**, storing only the current state.

```python
import sys

nums_list = [x for x in range(1_000_000)]
nums_gen = (x for x in range(1_000_000))

print("List size:", sys.getsizeof(nums_list))   # Very large
print("Generator size:", sys.getsizeof(nums_gen))  # Very small
```

👉 Output on most systems:

```
List size: ~8 MB
Generator size: ~112 bytes
```

---

## 2️⃣ Reading Large Files with a Generator

Instead of loading a huge file into memory, read it **line by line**:

```python
def read_file(path):
    with open(path) as f:
        for line in f:
            yield line

# Example usage
for i, line in enumerate(read_file("large_file.txt")):
    if i < 5:
        print(line.strip())
    else:
        break
```

✅ This way, only **one line** is in memory at a time, no matter the file size.

---

## 3️⃣ `range` vs `xrange` in Python 2

- In **Python 2**:
    
    - `range(n)` → creates a **list** in memory.
        
    - `xrange(n)` → **lazy evaluation** (like generator).
        
- In **Python 3**:
    
    - `range(n)` is lazy like `xrange`, so no separate `xrange`.
        

```python
r = range(10**7)   # Lazy in Python 3
print(sys.getsizeof(r))   # Very small
```

---

## 4️⃣ When to Use Generators

Use **generators** when:

- Working with **large data streams/files**
    
- You don’t need **random access** (no indexing like `list[5]`)
    
- You want to **save memory**
    
- You only need to process items **once**
    

---

## 🏋️ Exercise

👉 Compare memory usage of storing **1 million numbers** in a list vs a generator:

```python
import sys

nums_list = [i for i in range(1_000_000)]
nums_gen = (i for i in range(1_000_000))

print("Memory used by list:", sys.getsizeof(nums_list))
print("Memory used by generator:", sys.getsizeof(nums_gen))
```

📌 On a typical system:

```
Memory used by list: ~8,000,056 bytes
Memory used by generator: 112 bytes
```

---
