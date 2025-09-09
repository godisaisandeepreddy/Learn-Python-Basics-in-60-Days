Sorting is one of the **fundamental operations** in programming. Python provides efficient built-in methods, but understanding sorting algorithms helps you:

- Analyze performance
    
- Choose the right algorithm for your use case
    
- Understand complexity trade-offs
    

---

## 1️⃣ Built-in Sorting

Python provides two ways to sort:

```python
nums = [5, 2, 9, 1]

# Creates a new sorted list (does not modify original)
print(sorted(nums))     # [1, 2, 5, 9]

# Sorts in-place (modifies the list)
nums.sort()
print(nums)             # [1, 2, 5, 9]
```

---

## 2️⃣ Custom Sorting with `key`

You can customize sorting using a **function** or `lambda` with `key`.

```python
words = ["apple", "banana", "pear"]

# Sort by length
print(sorted(words, key=len))  
# ['pear', 'apple', 'banana']

# Sort case-insensitive
print(sorted(words, key=str.lower))  
```

---

## 3️⃣ Bubble Sort (O(n²))

- Compares adjacent elements and swaps if out of order.
    
- Repeats until list is sorted.
    

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):  # last i elements already sorted
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr

nums = [5, 2, 9, 1]
print(bubble_sort(nums))   # [1, 2, 5, 9]
```

🔹 **Complexity:**

- Worst case: O(n²)
    
- Best case: O(n) (if already sorted with optimization)
    

---

## 4️⃣ Insertion Sort (O(n²))

- Builds the sorted list one element at a time.
    
- Efficient for **small datasets** or **nearly sorted lists**.
    

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

nums = [5, 2, 9, 1]
print(insertion_sort(nums))   # [1, 2, 5, 9]
```

🔹 **Complexity:**

- Worst case: O(n²)
    
- Best case: O(n) (already sorted)
    

---

## 5️⃣ Python’s Timsort (O(n log n))

- Python’s built-in `sort()` uses **Timsort** → a hybrid of **merge sort** and **insertion sort**.
    
- **Optimized for real-world data** (handles partially sorted sequences very efficiently).
    
- Complexity:
    
    - Worst case: O(n log n)
        
    - Best case: O(n)
        

---

## 6️⃣ Exercise

🔹 **Compare Bubble Sort vs Python’s `sort()`**

```python
import random, time

# Generate large input
arr = [random.randint(0, 10000) for _ in range(5000)]

# Bubble sort timing
start = time.time()
bubble_sort(arr[:])  # copy to avoid modifying original
print("Bubble sort time:", time.time() - start)

# Built-in sort timing
start = time.time()
sorted(arr)
print("Built-in sort time:", time.time() - start)
```

👉 You’ll observe **Python’s sort is thousands of times faster** due to Timsort’s efficiency.

---

## 7️⃣ Key Takeaways

- Use Python’s built-in `sort()` (Timsort) in real-world applications.
    
- Bubble Sort & Insertion Sort are useful for **learning & very small inputs**.
    
- Always consider **time complexity** when choosing sorting algorithms.
    

---
