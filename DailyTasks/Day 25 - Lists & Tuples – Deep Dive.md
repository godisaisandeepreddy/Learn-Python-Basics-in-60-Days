Python provides **built-in data structures** like **lists and tuples**, which are essential for handling collections of data.

---

## 1️⃣ Lists

- **Mutable:** can change elements after creation.
    
- **Dynamic:** can grow or shrink dynamically.
    
- **Ordered:** preserves insertion order.
    

### 🔹 Common Operations

```python
nums = [1, 2, 3]

# Add elements
nums.append(4)           # [1, 2, 3, 4]
nums.extend([5, 6])      # [1, 2, 3, 4, 5, 6]
nums.insert(2, 99)       # insert 99 at index 2 → [1, 2, 99, 3, 4, 5, 6]

# Remove elements
nums.remove(99)           # [1, 2, 3, 4, 5, 6]
popped = nums.pop()       # remove last → 6
del nums[0]               # delete first element → [2, 3, 4, 5]

# Sorting
nums.sort()               # [2, 3, 4, 5]

# Indexing & slicing
print(nums[1])            # 3
print(nums[1:4])          # [3, 4, 5]

# Reverse
nums.reverse()            # [5, 4, 3, 2]
```

---

### 🔹 Nested Lists

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]

print(matrix[1][2])  # 6
```

---

## 2️⃣ Tuples

- **Immutable:** cannot modify after creation.
    
- **Faster:** due to immutability.
    
- **Ordered:** preserves insertion order.
    

### 🔹 Packing & Unpacking

```python
tup = (10, 20, 30)

# Unpacking
a, b, c = tup
print(a, b, c)  # 10 20 30

# Single element tuple
single = (5,)  # note the comma
```

### 🔹 Nested Tuples

```python
nested = ((1, 2), (3, 4))
print(nested[1][0])  # 3
```

---

## 3️⃣ When to Use Lists vs Tuples

|Feature|List|Tuple|
|---|---|---|
|Mutability|Mutable|Immutable|
|Performance|Slower|Faster|
|Use-case|Dynamic data|Fixed data|
|Methods|Many methods|Limited methods|

✅ Example: use tuple for coordinates `(x, y)` and list for a growing collection of user inputs.

---

## 4️⃣ Exercise: Rotate a List by `k` Positions

Rotate elements to the right by `k` positions.

```python
def rotate_list(lst, k):
    n = len(lst)
    k %= n  # handle k > n
    return lst[-k:] + lst[:-k]

nums = [1, 2, 3, 4, 5]
rotated = rotate_list(nums, 2)
print(rotated)  # [4, 5, 1, 2, 3]
```

---

### 5️⃣ Key Takeaways

- Lists are **flexible and mutable**, suitable for dynamic data.
    
- Tuples are **immutable and faster**, suitable for fixed collections.
    
- Nested lists/tuples allow **matrix-like structures**.
    
- Understanding **operations and slicing** is critical for manipulating sequences efficiently.
    

---
