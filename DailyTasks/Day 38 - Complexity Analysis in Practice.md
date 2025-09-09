
Now that you know **Big-O notation**, let’s see how it looks in **real performance tests**.

We’ll compare **different operations** and measure time using Python’s `time` and `timeit` modules.

---

## 1️⃣ Linear Search vs Binary Search

- **Linear Search (O(n))** → check every element.
    
- **Binary Search (O(log n))** → requires **sorted list**, halves search space each step.
    

```python
import bisect, random, time

nums = list(range(1_000_000))
target = random.randint(0, 999_999)

# Linear Search
start = time.time()
found = target in nums   # O(n)
end = time.time()
print("Linear search:", end - start)

# Binary Search
start = time.time()
pos = bisect.bisect_left(nums, target)   # O(log n)
end = time.time()
print("Binary search:", end - start)
```

👉 You’ll see **binary search is much faster** for large lists.

---

## 2️⃣ List Append vs Insert at Index 0

- `append()` adds to the **end** → **O(1)**.
    
- `insert(0, x)` adds to the **front** → **O(n)** (shifts elements).
    

```python
import time

nums = []

# Append
start = time.time()
for i in range(100000):
    nums.append(i)
end = time.time()
print("List append:", end - start)

# Insert at front
nums = []
start = time.time()
for i in range(100000):
    nums.insert(0, i)
end = time.time()
print("List insert at index 0:", end - start)
```

👉 Appending is **much faster**.

---

## 3️⃣ Dict Lookup vs List Lookup

- `dict` → hash table → **O(1)** lookup.
    
- `list` → must scan each element → **O(n)** lookup.
    

```python
nums_list = list(range(1_000_000))
nums_dict = {x: True for x in range(1_000_000)}

target = 999_999

import time

# List lookup
start = time.time()
found = target in nums_list
end = time.time()
print("List lookup:", end - start)

# Dict lookup
start = time.time()
found = target in nums_dict
end = time.time()
print("Dict lookup:", end - start)
```

👉 Dict lookup will be **almost instant**, while list lookup is slower.

---

## 4️⃣ Using `timeit` for Precise Measurement

`timeit` runs code **multiple times** to get accurate results.

```python
import timeit

print("List lookup:", timeit.timeit("999999 in list(range(1000000))", number=10))
print("Dict lookup:", timeit.timeit("999999 in {x:True for x in range(1000000)}", number=10))
```

---

## 🏋️ Exercise

👉 Write code to **compare search algorithms** on large inputs:

1. Linear search on unsorted list
    
2. Binary search on sorted list
    
3. Dict lookup
    
4. Set lookup
    

Record execution times and compare.

---

