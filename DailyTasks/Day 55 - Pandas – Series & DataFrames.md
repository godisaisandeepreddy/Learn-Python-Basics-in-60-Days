## 📌 1. What is Pandas?

- Pandas is a **Python library for data manipulation and analysis**.
    
- Provides two main data structures:
    
    1. **Series** → 1D labeled array
        
    2. **DataFrame** → 2D labeled table (rows & columns)
        

💡 Advantages: Easy data cleaning, filtering, aggregation, and file I/O.

---

## 📌 2. Pandas Series

A **Series** is like a column in Excel with **index labels**.

```python
import pandas as pd

# Create a Series
s = pd.Series([10, 20, 30], index=["a", "b", "c"])
print(s)
print(s["b"])        # Access by index
print(s.values)      # Numpy array
print(s.index)       # Index labels

# Series operations
print(s + 5)         # Vectorized addition
```

---

## 📌 3. Pandas DataFrame

A **DataFrame** is a table with rows and columns.

```python
# Create DataFrame from dictionary
data = {"name": ["Alice","Bob","Charlie"], "age": [25,30,35], "city": ["NY","LA","SF"]}
df = pd.DataFrame(data)

# Basic operations
print(df.head())      # First 5 rows
print(df.tail(2))     # Last 2 rows
print(df.shape)       # Rows, columns
print(df.columns)     # Column names
print(df["name"])     # Select column
print(df.loc[1])      # Select row by label
print(df.iloc[0])     # Select row by position
```

### Filtering & Conditional Selection

```python
# Age > 28
print(df[df["age"] > 28])

# Multiple conditions
print(df[(df["age"]>28) & (df["city"]=="SF")])
```

---

## 📌 4. Reading & Writing Files

```python
# CSV
df.to_csv("output.csv", index=False)
df = pd.read_csv("output.csv")

# Excel
df.to_excel("output.xlsx", index=False)
df = pd.read_excel("output.xlsx")

# JSON
df.to_json("output.json", orient="records")
df = pd.read_json("output.json")
```

---

## 🏋️ Exercise

1. Download a **CSV file** of sales data (or create dummy data).
    
2. Load it into a **DataFrame**.
    
3. Display the **top 5 rows** using `.head()`.
    
4. Filter sales > 5000 and display relevant rows.
    

---
