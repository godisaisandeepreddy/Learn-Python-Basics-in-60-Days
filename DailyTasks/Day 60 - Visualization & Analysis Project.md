## 📌 1. Pandas Plotting Basics

Pandas integrates with Matplotlib, allowing quick plots directly from DataFrames.

```python
import pandas as pd
import matplotlib.pyplot as plt

# Sample DataFrame
data = {
    "Month": ["Jan", "Feb", "Mar", "Apr"],
    "Sales": [250, 300, 400, 350]
}
df = pd.DataFrame(data)

# Line plot
df.plot(x="Month", y="Sales", kind="line", title="Monthly Sales Trend")
plt.show()

# Bar plot
df.plot(x="Month", y="Sales", kind="bar", color="skyblue")
plt.show()

# Pie chart
df.plot(y="Sales", kind="pie", labels=df["Month"], autopct="%1.1f%%")
plt.show()
```

---

## 📌 2. Matplotlib Basics

Matplotlib provides more flexibility for customizing plots:

```python
plt.figure(figsize=(8,5))
plt.plot(df["Month"], df["Sales"], marker="o", linestyle="--", color="green")
plt.title("Monthly Sales Trend")
plt.xlabel("Month")
plt.ylabel("Sales")
plt.grid(True)
plt.show()
```

- `marker` → point style
    
- `linestyle` → line type
    
- `color` → line color
    
- `grid` → show grid
    

---

## 📌 3. Mini Data Analysis Project

**Steps:**

1. **Load dataset (CSV)**
    

```python
covid_df = pd.read_csv("covid19_cases.csv")
print(covid_df.head())
```

2. **Clean missing values**
    

```python
covid_df.fillna(0, inplace=True)  # or dropna()
```

3. **Group & aggregate**
    

```python
cases_by_country = covid_df.groupby("Country")["Cases"].sum()
print(cases_by_country)
```

4. **Plot trends**
    

```python
cases_by_country.sort_values(ascending=False).head(10).plot(kind="bar", color="orange")
plt.title("Top 10 Countries by COVID-19 Cases")
plt.ylabel("Total Cases")
plt.show()
```

- Use **line plot** to show trends over time:
    

```python
country_df = covid_df[covid_df["Country"]=="India"]
country_df.plot(x="Date", y="Cases", kind="line", title="India COVID-19 Cases Trend")
plt.show()
```

---

## 🏋️ Exercise

1. Load a COVID-19 dataset (or any time-series dataset).
    
2. Clean missing values.
    
3. Group by country/region and aggregate total cases.
    
4. Plot **top 10 countries** using a bar chart.
    
5. Plot **trend line** for a single country.
    
6. Optional: Customize plots (colors, grid, markers, labels).
    

---
