Understanding **time complexity** is crucial to write **efficient code**. It tells us **how the runtime of an algorithm grows** with input size.

---

## 1️⃣ Concept of Algorithmic Complexity

- **Time complexity** → how runtime increases with input size `n`
    
- **Space complexity** → how memory usage increases with input size
    
- Helps in comparing **different algorithms** for the same task
    

### 🔹 Big-O Notation

- Expresses **upper bound** of runtime
    
- Focuses on **dominant operations** (ignores constants)
    

---

## 2️⃣ Common Complexities

|Complexity|Meaning|Example|
|---|---|---|
|O(1)|Constant time|Accessing element by index in a list|
|O(log n)|Logarithmic|Binary search in sorted list|
|O(n)|Linear|Searching element in unsorted list|
|O(n log n)|Linearithmic|Efficient sorting algorithms (merge sort, quick sort)|
|O(n²)|Quadratic|Nested loops for pair comparisons|

---

## 3️⃣ Example: Searching in List vs Dictionary

```python
nums = list(range(1000000))

# Linear search in list → O(n)
print(999999 in nums)  # True

# Dictionary lookup → O(1)
d = {x: True for x in range(1000000)}
print(999999 in d)     # True
```

✅ Notice: Dictionary lookup is **much faster** for large datasets due to hash-based access.

---

## 4️⃣ Exercise: Compare List Lookup vs Set Lookup

```python
import time

N = 10**7
nums = list(range(N))
nums_set = set(nums)

# List lookup
start = time.time()
9999999 in nums
end = time.time()
print("List lookup time:", end - start)

# Set lookup
start = time.time()
9999999 in nums_set
end = time.time()
print("Set lookup time:", end - start)
```

**Observation:**

- Lookup in list → grows linearly with `n`
    
- Lookup in set → remains almost constant
    

---

## 5️⃣ Key Takeaways

- **Big-O notation** helps reason about algorithm efficiency.
    
- Use **lists** for ordered collections, **sets/dicts** for fast membership lookups.
    
- Avoid **nested loops** where possible → O(n²) is expensive for large `n`.
    
- Practicing **empirical comparison** (timing code) helps **understand complexity practically**.
    

---

