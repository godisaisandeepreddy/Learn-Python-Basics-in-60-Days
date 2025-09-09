(HOFs: `map`, `filter`, `zip`, `enumerate`)

A **Higher-Order Function (HOF)** is a function that can:

- Accept other functions as arguments, OR
    
- Return a function.
    

In Python, we often use **lambda functions** with HOFs for concise, powerful data transformations.

---

## 1️⃣ `map()`

- Applies a function to **every element** in an iterable (list, tuple, etc.).
    
- Returns a `map` object (convert with `list()`).
    

### Example 1 – Square numbers

```python
nums = [1, 2, 3, 4, 5]
squares = list(map(lambda x: x**2, nums))
print(squares)  # [1, 4, 9, 16, 25]
```

### Example 2 – Convert strings to uppercase

```python
words = ["apple", "banana", "cherry"]
upper_words = list(map(str.upper, words))
print(upper_words)  # ['APPLE', 'BANANA', 'CHERRY']
```

---

## 2️⃣ `filter()`

- Filters items from an iterable based on a condition.
    
- Function must return **True/False**.
    

### Example 1 – Keep even numbers

```python
nums = [10, 15, 20, 25, 30]
evens = list(filter(lambda x: x % 2 == 0, nums))
print(evens)  # [10, 20, 30]
```

### Example 2 – Extract short words

```python
words = ["apple", "banana", "kiwi", "grape"]
short_words = list(filter(lambda w: len(w) <= 4, words))
print(short_words)  # ['kiwi']
```

---

## 3️⃣ `zip()`

- Combines multiple iterables into tuples, element by element.
    
- Stops at the **shortest iterable**.
    

### Example 1 – Pairing elements

```python
names = ["Alice", "Bob", "Charlie"]
scores = [85, 90, 95]
zipped = list(zip(names, scores))
print(zipped)  # [('Alice', 85), ('Bob', 90), ('Charlie', 95)]
```

### Example 2 – Unzipping with `*`

```python
zipped = [('Alice', 85), ('Bob', 90), ('Charlie', 95)]
names, scores = zip(*zipped)
print(names)   # ('Alice', 'Bob', 'Charlie')
print(scores)  # (85, 90, 95)
```

---

## 4️⃣ `enumerate()`

- Adds an **index** to an iterable.
    
- Useful in loops when you need both index and value.
    

### Example 1 – Basic enumerate

```python
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(index, fruit)
```

✅ Output:

```
0 apple
1 banana
2 cherry
```

### Example 2 – Custom start index

```python
for index, fruit in enumerate(fruits, start=1):
    print(index, fruit)
```

✅ Output:

```
1 apple
2 banana
3 cherry
```

---

## 5️⃣ Combining HOFs

You can chain them for more complex tasks.

```python
nums = [1, 2, 3, 4, 5, 6]

# Double each number, then keep only > 5
result = list(filter(lambda x: x > 5, map(lambda x: x * 2, nums)))
print(result)  # [6, 8, 10, 12]
```

---

## 6️⃣ Best Practices

✅ Use `map`/`filter` with `lambda` for short, inline logic.  
✅ For more readability, prefer list comprehensions when possible:

```python
nums = [1, 2, 3, 4, 5]
squares = [x**2 for x in nums]  # instead of map
```

---

## 7️⃣ Exercises

1. Use `map()` to convert a list of Fahrenheit temps `[32, 68, 100]` into Celsius.
    
2. Use `filter()` to get all names longer than 4 characters from `["Tom", "Jerry", "Mickey", "Donald"]`.
    
3. Use `zip()` to combine `["a", "b", "c"]` and `[1, 2, 3]`.
    
4. Use `enumerate()` to print elements of `["red", "green", "blue"]` starting index at `100`.
    
5. Combine `map()` + `filter()` to first **square numbers** from `[1,2,3,4,5,6]` and then keep only numbers greater than 10.
    

---

✅ By the end of Day 13 → You’ll master Python’s built-in HOFs that make functional-style programming easy.

---
