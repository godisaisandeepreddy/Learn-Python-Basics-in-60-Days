## 📌 1. GroupBy & Aggregation

- Group rows based on column values and compute aggregate metrics.
    

```python
import pandas as pd

data = {
    "employee": ["Alice","Bob","Charlie","David","Eve"],
    "department": ["HR","IT","IT","HR","IT"],
    "salary": [5000, 6000, 7000, 5500, 6500]
}

df = pd.DataFrame(data)

# Average salary by department
avg_salary = df.groupby("department")["salary"].mean()
print(avg_salary)

# Multiple aggregations
agg_salary = df.groupby("department")["salary"].agg(["mean","sum","max"])
print(agg_salary)
```

---

## 📌 2. Merging, Joining & Concatenation

- Combine multiple datasets using **merge** or **concat**
    

```python
df1 = pd.DataFrame({"employee":["Alice","Bob"], "age":[25,30]})
df2 = pd.DataFrame({"employee":["Alice","Bob"], "salary":[5000,6000]})

# Merge on a common column
merged = pd.merge(df1, df2, on="employee")
print(merged)

# Concatenation (stacking)
concat_df = pd.concat([df1, df2], axis=0)  # vertical
print(concat_df)
```

---

## 📌 3. Sorting & Ranking

```python
# Sort by salary descending
print(df.sort_values("salary", ascending=False))

# Ranking salaries
df["rank"] = df["salary"].rank(ascending=False)
print(df)
```

---

## 📌 4. Working with Dates & Time Series

```python
date_data = {
    "date": ["2025-01-01","2025-01-02","2025-01-03","2025-01-04"],
    "sales": [200, 250, 300, 220]
}

df_date = pd.DataFrame(date_data)
df_date["date"] = pd.to_datetime(df_date["date"])

# Set as index
df_date.set_index("date", inplace=True)

# Resample daily/weekly/monthly
weekly_sales = df_date.resample("D").sum()  # D=Day, W=Week, M=Month
print(weekly_sales)

# Access year, month, day
print(df_date.index.year)
print(df_date.index.month)
```

---

## 🏋️ Exercise

1. Load an **employee dataset** with columns: department, salary, date_of_joining.
    
2. Compute **average salary per department**.
    
3. Sort departments by **average salary**.
    
4. For a sales dataset, **resample daily/weekly sales** and compute totals.
    

---
