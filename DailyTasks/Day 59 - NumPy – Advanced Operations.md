
## 📌 1. Mathematical Functions

NumPy provides **vectorized mathematical functions**, which allow element-wise operations on arrays efficiently.

```python
import numpy as np

arr = np.array([0, np.pi/2, np.pi])

# Trigonometric functions
print("sin:", np.sin(arr))
print("cos:", np.cos(arr))
print("tan:", np.tan(arr))

# Square root
print("sqrt:", np.sqrt([1, 4, 9, 16]))

# Exponential
print("exp:", np.exp([1, 2, 3]))
```

**Tip:** These operations are **faster than iterating over Python lists** because they are implemented in C under the hood.

---

## 📌 2. Random Number Generation

NumPy's `random` module allows generation of random numbers and arrays, which is useful for simulations and probabilistic computations.

```python
# Random floats between 0 and 1
rand_floats = np.random.rand(5)
print("Random floats:", rand_floats)

# Random integers in a range
rand_ints = np.random.randint(1, 7, size=10)  # simulate dice rolls
print("Random integers (dice):", rand_ints)

# Normally distributed random numbers
normal_dist = np.random.randn(5)
print("Normal distribution:", normal_dist)
```

---

## 📌 3. Concatenation & Splitting

- **Concatenate arrays**
    

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
c = np.concatenate([a, b])
print("Concatenated:", c)
```

- **Split arrays**
    

```python
arr2 = np.arange(10)
split_arr = np.array_split(arr2, 3)
print("Split array:", split_arr)
```

- **2D arrays concatenation**
    

```python
arr_2d = np.arange(1, 10).reshape(3, 3)
# Vertical concatenation
print(np.concatenate([arr_2d, arr_2d], axis=0))
# Horizontal concatenation
print(np.concatenate([arr_2d, arr_2d], axis=1))
```

---

## 📌 4. Linear Algebra Basics

NumPy supports **matrix operations** essential for scientific computing and machine learning.

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

# Matrix multiplication
C = np.dot(A, B)
print("Dot product:\n", C)

# Using @ operator for matrix multiplication
C2 = A @ B
print("Matrix multiplication using @:\n", C2)

# Transpose
print("Transpose of A:\n", A.T)
```

---

## 🏋️ Exercise

1. Simulate **1000 dice rolls**:
    

```python
rolls = np.random.randint(1, 7, 1000)
```

2. Compute **frequency of each face (1–6)**:
    

```python
faces, counts = np.unique(rolls, return_counts=True)
for face, count in zip(faces, counts):
    print(f"Face {face}: {count} times, Probability: {count/1000:.2f}")
```

3. (Optional) Plot the **probability distribution** using matplotlib.
    
4. Compute **mean and standard deviation**:
    

```python
print("Mean:", np.mean(rolls))
print("Std Dev:", np.std(rolls))
```

---
