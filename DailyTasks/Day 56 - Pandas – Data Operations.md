
## 📌 1. Indexing & Slicing

- Select columns:
    

```python
import pandas as pd

data = {"name": ["Alice","Bob","Charlie"], "age": [25,30,35], "city": ["NY","LA","SF"]}
df = pd.DataFrame(data)

# Single column
print(df["name"])

# Multiple columns
print(df[["name","city"]])
```

- Select rows by **position** or **label**:
    

```python
# By position
print(df.iloc[0:2])   # First two rows

# By label
print(df.loc[0:1, ["name","age"]])
```

---

## 📌 2. Filtering & Conditional Selection

```python
# Age greater than 25
filtered = df[df["age"] > 25]
print(filtered)

# Multiple conditions
filtered2 = df[(df["age"]>25) & (df["city"]=="SF")]
print(filtered2)
```

---

## 📌 3. Adding & Removing Columns

```python
# Adding a new column
df["salary"] = [5000, 6000, 7000]
print(df)

# Removing a column
df.drop("salary", axis=1, inplace=True)
print(df)
```

---

## 📌 4. Handling Missing Values

```python
import numpy as np

df2 = pd.DataFrame({
    "name": ["Alice","Bob","Charlie","David"],
    "age": [25, np.nan, 35, 40],
    "city": ["NY", "LA", np.nan, "SF"]
})

# Drop rows with missing values
print(df2.dropna())

# Fill missing values
df2["age"].fillna(df2["age"].mean(), inplace=True)
df2["city"].fillna("Unknown", inplace=True)
print(df2)
```

---

## 📌 5. Aggregations

```python
# Sum & mean
print(df2["age"].sum())
print(df2["age"].mean())

# Value counts
print(df2["city"].value_counts())
```

---

## 🏋️ Exercise

1. Load a dataset (CSV or Excel) with **missing values**.
    
2. Fill missing numeric columns with **mean**, categorical with **mode** or custom value.
    
3. Compute **average age**, **total salary**, or other relevant statistics.
    
4. Filter rows based on conditions like age > 30 or city == "NY".
    

---
