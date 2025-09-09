
---

## 1️⃣ What is a List?

- A **list** is an **ordered, mutable collection** of items.
    
- Can store **different data types** (int, str, float, etc.).
    
- Defined with **square brackets `[]`**.
    

```python
numbers = [10, 20, 30, 40]
mixed = [1, "apple", 3.5, True]
nested = [[1, 2], [3, 4]]
```

---

## 2️⃣ Indexing & Slicing

```python
fruits = ["apple", "banana", "cherry", "date"]

print(fruits[0])    # apple
print(fruits[-1])   # date
print(fruits[1:3])  # ['banana', 'cherry']
print(fruits[:2])   # ['apple', 'banana']
print(fruits[::2])  # ['apple', 'cherry']
```

---

## 3️⃣ List Operations

### 🔹 Concatenation & Repetition

```python
a = [1, 2, 3]
b = [4, 5]

print(a + b)     # [1, 2, 3, 4, 5]
print(a * 2)     # [1, 2, 3, 1, 2, 3]
```

### 🔹 Membership

```python
print(2 in a)      # True
print(10 not in a) # True
```

---

## 4️⃣ Modifying Lists

```python
nums = [10, 20, 30]

nums[1] = 99        # change element
print(nums)         # [10, 99, 30]

nums.append(40)     # add element
nums.insert(1, 15)  # insert at index
print(nums)         # [10, 15, 99, 30, 40]

nums.remove(99)     # remove element
popped = nums.pop() # remove last element
print(popped)       # 40
del nums[0]         # delete by index
print(nums)         # [15, 30]
```

---

## 5️⃣ Useful List Methods

```python
data = [3, 1, 4, 1, 5, 9]

print(len(data))       # 6
print(min(data))       # 1
print(max(data))       # 9
print(data.count(1))   # 2

data.sort()            # sort ascending
print(data)            # [1, 1, 3, 4, 5, 9]

data.reverse()         # reverse list
print(data)            # [9, 5, 4, 3, 1, 1]

copy_list = data.copy()
print(copy_list)
```

---

## 6️⃣ Iterating Over Lists

```python
fruits = ["apple", "banana", "cherry"]

# For loop
for f in fruits:
    print(f)

# While loop
i = 0
while i < len(fruits):
    print(fruits[i])
    i += 1
```

---

## 7️⃣ List Comprehensions

A **short way** to create lists.

```python
# Normal way
squares = []
for i in range(5):
    squares.append(i*i)

# List comprehension
squares = [i*i for i in range(5)]
print(squares)  # [0, 1, 4, 9, 16]

# With condition
evens = [x for x in range(10) if x % 2 == 0]
print(evens)  # [0, 2, 4, 6, 8]
```

---

## 8️⃣ Nested Lists

```python
matrix = [[1, 2], [3, 4], [5, 6]]

# Access elements
print(matrix[0][1])  # 2

# Flatten list
flat = [num for row in matrix for num in row]
print(flat)  # [1, 2, 3, 4, 5, 6]
```

---

## 9️⃣ Day 5 Exercises

1. Create a list of your **5 favorite movies** and print the first and last one.
    
2. Write a program to add a new fruit `"mango"` to a list and remove `"banana"`.
    
3. Sort the list `[9, 3, 6, 1, 8]` in ascending and descending order.
    
4. Use slicing to get every **second element** from `[10, 20, 30, 40, 50]`.
    
5. Write a program that squares numbers from `1–10` using list comprehension.
    
6. Given `matrix = [[1,2,3],[4,5,6],[7,8,9]]`, print the diagonal elements `[1,5,9]`.
    
7. Take a list of numbers and print only the **even ones** using list comprehension.
    
8. Copy a list, change the copy, and confirm the original is unchanged.
    

---

✅ By end of Day 5 → You’ll be able to **create, modify, slice, iterate, and use comprehensions with lists**.

---
