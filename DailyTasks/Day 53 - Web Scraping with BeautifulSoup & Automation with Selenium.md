## 📌 1. Web Scraping with BeautifulSoup

Install required packages:

```bash
pip install requests beautifulsoup4
```

### Basic Example

```python
from bs4 import BeautifulSoup
import requests

url = "https://example.com"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

# Get page title
print(soup.title.string)

# Find all links
for link in soup.find_all("a"):
    print(link.get("href"))
```

### Parsing Tables

```python
table = soup.find("table")
for row in table.find_all("tr"):
    cols = row.find_all("td")
    data = [col.text.strip() for col in cols]
    print(data)
```

---

## 📌 2. Automation with Selenium

Install Selenium and browser driver:

```bash
pip install selenium
```

### Basic Selenium Usage

```python
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()  # Ensure chromedriver is in PATH
driver.get("https://example.com")

# Find element
search_box = driver.find_element(By.NAME, "q")
search_box.send_keys("Python")
search_box.submit()

# Click button
# button = driver.find_element(By.ID, "submit-btn")
# button.click()

driver.quit()
```

💡 Selenium is useful for sites that **require interaction** or use **JavaScript** heavily.

---

## 📌 3. Saving Data to CSV

```python
import csv

data = [["Product", "Price"], ["Laptop", "$1200"], ["Phone", "$500"]]

with open("products.csv", "w", newline="") as f:
    writer = csv.writer(f)
    writer.writerows(data)
```

---

## 🏋️ Exercise

👉 Scrape **product prices** from an e-commerce website:

1. Extract product name & price.
    
2. Save results to CSV.
    
3. Optional: Use Selenium if the page requires scrolling or clicking “Load More”.
    

---
