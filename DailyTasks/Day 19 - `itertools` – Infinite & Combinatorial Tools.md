
The `itertools` module provides **fast, memory-efficient tools** for creating iterators.  
Useful for **loops, combinations, permutations, and infinite sequences**.

---

## 1️⃣ Infinite Iterators

These generate values endlessly (stop with conditions).

```python
import itertools

# count(start, step) → infinite sequence
for i in itertools.count(5, 2):
    if i > 15:
        break
    print(i, end=" ")  # 5 7 9 11 13 15

# cycle(iterable) → repeat forever
count = 0
for color in itertools.cycle(["red", "green", "blue"]):
    print(color, end=" ")
    count += 1
    if count == 6:
        break  # red green blue red green blue

# repeat(elem, times) → repeat n times
for x in itertools.repeat("Hi", 3):
    print(x)  # Hi Hi Hi
```

---

## 2️⃣ Combinatoric Iterators

### 🔹 `product()` – Cartesian product (like nested loops)

```python
from itertools import product

print(list(product([1, 2], ["a", "b"])))
# [(1, 'a'), (1, 'b'), (2, 'a'), (2, 'b')]
```

### 🔹 `permutations()` – All possible orderings

```python
from itertools import permutations

print(list(permutations([1, 2, 3], 2)))
# [(1, 2), (1, 3), (2, 1), (2, 3), (3, 1), (3, 2)]
```

### 🔹 `combinations()` – Unique combinations

```python
from itertools import combinations

print(list(combinations([1, 2, 3], 2)))
# [(1, 2), (1, 3), (2, 3)]
```

### 🔹 `combinations_with_replacement()` – Reuse allowed

```python
from itertools import combinations_with_replacement

print(list(combinations_with_replacement([1, 2, 3], 2)))
# [(1, 1), (1, 2), (1, 3), (2, 2), (2, 3), (3, 3)]
```

---

## 3️⃣ Utility Iterators

### 🔹 `accumulate()` – Running totals

```python
from itertools import accumulate

nums = [1, 2, 3, 4]
print(list(accumulate(nums)))  
# [1, 3, 6, 10]
```

### 🔹 `chain()` – Combine multiple iterables

```python
from itertools import chain

print(list(chain("ABC", "123")))
# ['A', 'B', 'C', '1', '2', '3']
```

### 🔹 `groupby()` – Group consecutive values

```python
from itertools import groupby

data = [("fruit", "apple"), ("fruit", "banana"), ("veg", "carrot"), ("veg", "potato")]

for key, group in groupby(data, key=lambda x: x[0]):
    print(key, list(group))

# fruit [('fruit', 'apple'), ('fruit', 'banana')]
# veg [('veg', 'carrot'), ('veg', 'potato')]
```

---

## 4️⃣ Exercises

### 🔹 Exercise 1

Use `count()` and `islice()` to print the first 10 even numbers.

```python
import itertools
print(list(itertools.islice(itertools.count(2, 2), 10)))
# [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```

### 🔹 Exercise 2

Generate all **3-letter passwords** using `"abc"` (allow repetition).

```python
from itertools import product
print(["".join(p) for p in product("abc", repeat=3)])
```

### 🔹 Exercise 3

Use `accumulate()` to calculate running **product** instead of sum.

```python
import itertools, operator
nums = [1, 2, 3, 4]
print(list(itertools.accumulate(nums, operator.mul)))
# [1, 2, 6, 24]
```

---

✅ By the end of **Day 19** → You’ll know how to use `itertools` for **infinite sequences, combinatorics, and efficient looping utilities**.

---

👉 Do you want me to now prepare **Day 20: `os` and `sys` – System Interaction** in the same structured way?