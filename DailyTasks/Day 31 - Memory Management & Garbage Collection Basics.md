Understanding **memory management** is essential for writing **efficient Python programs** and avoiding memory leaks.

---

## 1️⃣ Python Memory Model

- Python manages memory **automatically**.
    
- **Objects** are stored in the **heap**, a region of memory for dynamic allocation.
    
- **Variables** are references (pointers) to objects in the heap.
    

```python
a = [1, 2, 3]
b = a  # b references the same object
```

✅ Modifying `b` will affect `a` because both refer to the same object.

---

## 2️⃣ Reference Counting

- Python keeps track of **how many references exist to each object**.
    
- When reference count drops to zero → memory is released.
    

```python
import sys

a = [1, 2, 3]
b = a
print(sys.getrefcount(a))  # e.g., 3 (variable a, b, and temporary reference in getrefcount)
del b
print(sys.getrefcount(a))  # decreased by 1
```

---

## 3️⃣ Garbage Collection (GC)

- Reference counting alone cannot handle **circular references**.
    
- **Circular reference example:**
    

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

a = Node(1)
b = Node(2)
a.next = b
b.next = a  # circular reference
```

- Python uses the **`gc` module** to detect and clean such cycles.
    

```python
import gc

print(gc.get_threshold())  # current thresholds for collection
gc.collect()               # force garbage collection
```

---

## 4️⃣ `del` Keyword and Object Lifecycle

- `del` removes a **reference** to an object.
    
- Object is only destroyed when **reference count = 0**.
    

```python
x = [1,2,3]
y = x
del x
print(y)  # still exists
del y
# object is now eligible for garbage collection
```

---

## 5️⃣ Exercise: Circular References & GC

```python
import gc

class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

# Create circular references
a = Node(1)
b = Node(2)
a.next = b
b.next = a

# Delete references
del a
del b

# Check garbage collector
unreachable = gc.collect()
print("Unreachable objects collected:", unreachable)
```

**Observation:**

- Circular references are **not freed immediately by reference counting**.
    
- **`gc.collect()`** manually cleans them up.
    

---

### 6️⃣ Key Takeaways

- Python automatically manages memory using **reference counting + garbage collection**.
    
- Circular references require **GC to free memory**.
    
- `del` removes references but does not always free memory immediately.
    
- Using `gc` module helps **monitor memory and debug leaks**.
    

---
