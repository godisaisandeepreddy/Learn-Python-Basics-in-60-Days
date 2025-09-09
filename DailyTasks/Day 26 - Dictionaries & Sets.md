Python provides **dictionaries and sets** as built-in data structures for **efficient lookup and unique collections**.

---

## 1️⃣ Dictionaries

- **Key-value store:** maps keys to values.
    
- **Fast lookup:** O(1) average time complexity.
    
- **Mutable:** can add, remove, and modify elements.
    

### 🔹 Creating a Dictionary

```python
student = {"name": "Alice", "age": 21, "grade": "A"}

# Access values
print(student["name"])         # Alice
print(student.get("age"))      # 21
print(student.get("roll", 0))  # 0 (default if key not found)

# Add / Update
student["age"] = 22
student["roll"] = 101

# Remove
del student["grade"]
removed = student.pop("roll")
```

### 🔹 Useful Methods

```python
print(student.keys())    # dict_keys(['name', 'age'])
print(student.values())  # dict_values(['Alice', 22])
print(student.items())   # dict_items([('name', 'Alice'), ('age', 22)])
```

### 🔹 Nested Dictionaries

```python
students = {
    "Alice": {"age": 21, "grade": "A"},
    "Bob": {"age": 22, "grade": "B"}
}

print(students["Bob"]["grade"])  # B
```

---

## 2️⃣ Sets

- **Unordered collection of unique elements.**
    
- Useful for **membership testing and mathematical operations**.
    

### 🔹 Creating Sets

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

# Add / Remove
a.add(5)
a.remove(1)

# Set operations
print(a | b)  # union → {2, 3, 4, 5, 6}
print(a & b)  # intersection → {3, 4, 5}
print(a - b)  # difference → {2}
print(a ^ b)  # symmetric difference → {2, 6}
```

### 🔹 Frozenset (Immutable Set)

```python
fs = frozenset([1, 2, 3])
# fs.add(4) → Error: cannot modify
```

---

## 3️⃣ Performance: Dict vs Set vs List

|Data Structure|Lookup|Insert|Memory|
|---|---|---|---|
|List|O(n)|O(1)|Low|
|Dict|O(1)|O(1)|High|
|Set|O(1)|O(1)|Medium|

✅ Use **dict** for key-value mapping, **set** for uniqueness and fast membership, **list** for ordered collections.

---

## 4️⃣ Exercise: Unique Words & Frequencies

```python
text = "Python is easy and Python is powerful. Python is popular."

# Split into words, normalize to lowercase
words = text.lower().replace(".", "").split()

# Count frequencies using dictionary
freq = {}
for word in words:
    freq[word] = freq.get(word, 0) + 1

print(freq)
# {'python': 3, 'is': 3, 'easy': 1, 'and': 1, 'powerful': 1, 'popular': 1}

# Optional: Using Counter from collections
from collections import Counter
print(Counter(words))
```

---

### 5️⃣ Key Takeaways

- **Dictionaries** → fast key-value storage, perfect for mapping data.
    
- **Sets** → unique elements and fast membership testing.
    
- **Frozenset** → immutable set, useful as dict keys.
    
- Combining **dicts and sets** with loops enables efficient text/data analysis.
    

---
