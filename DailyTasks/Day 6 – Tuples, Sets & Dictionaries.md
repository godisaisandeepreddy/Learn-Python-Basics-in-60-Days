
---

## 1️⃣ Tuples

- A **tuple** is an **ordered, immutable collection**.
    
- Defined using **parentheses `()`**.
    
- Used when data should **not be modified**.
    

```python
fruits = ("apple", "banana", "cherry")
```

### 🔹 Accessing Elements

```python
print(fruits[0])   # apple
print(fruits[-1])  # cherry
```

### 🔹 Tuple Operations

```python
t = (1, 2, 3, 4, 2)

print(len(t))       # 5
print(t.count(2))   # 2
print(t.index(3))   # 2 (position of element)
```

### 🔹 Single Element Tuple

```python
single = (5,)   # must include comma
```

✅ **Use Case**: Tuples are good for **fixed data** (e.g., coordinates `(x, y)`, RGB values).

---

## 2️⃣ Sets

- A **set** is an **unordered, mutable collection of unique items**.
    
- Defined using **curly braces `{}`** or `set()` constructor.
    

```python
nums = {1, 2, 3, 4, 4}
print(nums)  # {1, 2, 3, 4} (duplicates removed)
```

### 🔹 Adding & Removing Elements

```python
nums.add(5)
nums.remove(2)     # Error if not found
nums.discard(10)   # Safe remove (no error)
```

### 🔹 Set Operations

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)  # Union {1,2,3,4,5}
print(a & b)  # Intersection {3}
print(a - b)  # Difference {1,2}
print(a ^ b)  # Symmetric difference {1,2,4,5}
```

✅ **Use Case**: Sets are great for **removing duplicates** and performing **mathematical set operations**.

---

## 3️⃣ Dictionaries

- A **dictionary** is a collection of **key-value pairs**.
    
- Keys must be **unique and immutable** (e.g., strings, numbers, tuples).
    
- Defined using **curly braces `{}`**.
    

```python
student = {"name": "Alice", "age": 20, "grade": "A"}
```

### 🔹 Accessing Values

```python
print(student["name"])       # Alice
print(student.get("age"))    # 20
print(student.get("email", "Not Found"))  # Default value if key missing
```

### 🔹 Adding & Updating

```python
student["age"] = 21
student["city"] = "New York"
```

### 🔹 Removing

```python
student.pop("grade")       # remove key
del student["city"]        # delete key
student.clear()            # empty dictionary
```

### 🔹 Iterating

```python
student = {"name": "Bob", "age": 25, "grade": "B"}

for key in student:
    print(key, ":", student[key])

for key, value in student.items():
    print(key, "->", value)

print(student.keys())   # dict_keys(['name', 'age', 'grade'])
print(student.values()) # dict_values(['Bob', 25, 'B'])
```

✅ **Use Case**: Dictionaries are best for **mapping data** (like a mini database: name → phone number).

---

## 4️⃣ Day 6 Exercises

1. Create a tuple of 5 favorite foods. Try accessing the 2nd and last item.
    
2. Write a program to count how many times `10` appears in `(5, 10, 15, 10, 20, 10)`.
    
3. Create a set from `[1, 2, 2, 3, 4, 4, 5]` and print it (observe duplicates).
    
4. Perform union, intersection, and difference on sets `{1,2,3,4}` and `{3,4,5,6}`.
    
5. Create a dictionary `person = {"name": "John", "age": 30, "city": "London"}`.
    
    - Print the name.
        
    - Add `"email": "john@example.com"`.
        
    - Update age to 31.
        
    - Delete city.
        
6. Loop through a dictionary of 3 countries and their capitals, and print them.
    
7. Use `.get()` to safely retrieve a missing key without error.
    
8. Write a program that counts word frequencies in `"apple banana apple cherry banana apple"` using a dictionary.
    

---

✅ By end of Day 6 → You’ll master **Tuples, Sets, and Dictionaries – with CRUD operations and real-world use cases**.

---
