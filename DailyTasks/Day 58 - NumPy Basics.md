
## 📌 1. NumPy vs Python Lists

- **NumPy arrays** are **faster** and support **vectorized operations**.
    
- Memory efficient and allow **multidimensional arrays**.
    

```python
import numpy as np
import time

# Python list
py_list = list(range(1000000))
start = time.time()
py_list = [x*2 for x in py_list]
print("Python list time:", time.time() - start)

# NumPy array
np_arr = np.arange(1000000)
start = time.time()
np_arr = np_arr * 2
print("NumPy array time:", time.time() - start)
```

---

## 📌 2. Creating NumPy Arrays

```python
# From list
arr1 = np.array([1,2,3,4])

# Zeros & Ones
arr2 = np.zeros((3,3))
arr3 = np.ones((2,4))

# Range of numbers
arr4 = np.arange(0,10,2)    # 0 to 8 step 2

# Linearly spaced
arr5 = np.linspace(0,1,5)   # 5 values from 0 to 1

print(arr1, arr2, arr3, arr4, arr5)
```

---

## 📌 3. Indexing, Slicing, Reshaping

```python
arr = np.arange(1,10).reshape(3,3)
print(arr)

# Access element
print(arr[0,1])   # row 0, col 1

# Slice
print(arr[:,1])   # all rows, col 1
print(arr[1,:])   # row 1, all cols

# Flatten
print(arr.flatten())
```

---

## 📌 4. Element-wise Operations

```python
a = np.array([1,2,3])
b = np.array([4,5,6])

print(a + b)   # [5 7 9]
print(a * b)   # [4 10 18]
print(a ** 2)  # [1 4 9]
```

---

## 📌 5. Broadcasting

- Allows operations on arrays of different shapes.
    

```python
arr = np.array([[1,2,3],[4,5,6]])
print(arr + 10)     # Add scalar to all elements

col = np.array([1,0,1])
print(arr + col)    # Broadcast along rows
```

---

## 🏋️ Exercise

1. Create a **5x5 NumPy array** with values 1–25.
    
2. Compute **sum of each row**.
    
3. Compute **sum of each column**.
    
4. Multiply the entire array by 2 using **broadcasting**.
    

---

