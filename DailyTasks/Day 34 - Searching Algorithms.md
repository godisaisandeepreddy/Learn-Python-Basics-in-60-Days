Searching is another fundamental concept in computer science. You’ll often need to find whether an item exists in a collection and if so, at what position.

---

## 1️⃣ Linear Search (O(n))

- Go through each element until you find the target.
    
- Works on **unsorted data**.
    

```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i  # index found
    return -1  # not found

nums = [5, 3, 7, 1, 9]
print(linear_search(nums, 7))   # 2
print(linear_search(nums, 4))   # -1
```

🔹 **Complexity:** O(n)  
🔹 **When to use:** Small lists, or when the data is unsorted.

---

## 2️⃣ Binary Search (O(log n))

- Works only on **sorted data**.
    
- Divide & Conquer: repeatedly cut the search space in half.
    

```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

nums = [1, 3, 4, 7, 10]
print(binary_search(nums, 7))   # 3
print(binary_search(nums, 5))   # -1
```

🔹 **Complexity:** O(log n)  
🔹 **When to use:** Large, sorted datasets.

---

## 3️⃣ Binary Search with Recursion

```python
def binary_search_recursive(arr, target, left, right):
    if left > right:
        return -1
    mid = (left + right) // 2
    if arr[mid] == target:
        return mid
    elif arr[mid] < target:
        return binary_search_recursive(arr, target, mid + 1, right)
    else:
        return binary_search_recursive(arr, target, left, mid - 1)

nums = [1, 3, 4, 7, 10]
print(binary_search_recursive(nums, 7, 0, len(nums)-1))   # 3
print(binary_search_recursive(nums, 5, 0, len(nums)-1))   # -1
```

---

## 4️⃣ `bisect` Module (Binary Search Helper)

Python provides the **`bisect` module** for working with sorted lists.

```python
import bisect

nums = [1, 3, 4, 7, 10]
pos = bisect.bisect_left(nums, 7)
print("Found at index:", pos)   # 3
```

- `bisect_left` → position to insert while keeping sorted order (search from left).
    
- `bisect_right` → search from right.
    

---

## 5️⃣ Hash-based Search (O(1) average case)

Dictionaries and Sets use **hashing** → fastest way to search.

```python
# Using dict
d = {"apple": 1, "banana": 2, "pear": 3}
print("banana" in d)   # True

# Using set
s = {1, 3, 5, 7}
print(5 in s)          # True
```

🔹 **Complexity:** O(1) average, O(n) worst case (rare collisions).  
🔹 **When to use:** Fast lookups, membership checks.

---

## 6️⃣ Exercise

👉 Implement **binary search recursively** (done above).  
👉 Compare **linear vs binary search time** for large datasets.

```python
import time

arr = list(range(1000000))
target = 999999

# Linear search
start = time.time()
linear_search(arr, target)
print("Linear search:", time.time() - start)

# Binary search
start = time.time()
binary_search(arr, target)
print("Binary search:", time.time() - start)
```

💡 You’ll see **binary search is much faster** for large, sorted lists.

---
