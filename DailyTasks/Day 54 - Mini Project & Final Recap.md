## 📌 1. Logging in Python

### Logging Levels

|Level|Description|
|---|---|
|DEBUG|Detailed info for debugging|
|INFO|General events|
|WARNING|Something unexpected but non-critical|
|ERROR|Serious problem|
|CRITICAL|Very serious error|

### Basic Logging Setup

```python
import logging

logging.basicConfig(
    filename="app.log",
    level=logging.INFO,
    format="%(asctime)s [%(levelname)s] %(message)s"
)

logging.debug("Debugging info")
logging.info("App started")
logging.warning("This is a warning")
logging.error("An error occurred")
logging.critical("Critical issue!")
```

💡 In production, you might use **RotatingFileHandler** to manage log file sizes.

---

## 📌 2. Debugging with `pdb`

Python’s built-in debugger allows step-by-step execution:

```python
import pdb

def divide(a, b):
    pdb.set_trace()  # Execution stops here
    return a / b

print(divide(10, 0))
```

Commands:

- `n` → next line
    
- `s` → step into function
    
- `c` → continue execution
    
- `q` → quit debugger
    

---

## 📌 3. Final Recap

- **APIs**: `requests`, Flask, FastAPI, path/query params, CRUD operations
    
- **Web Scraping**: BeautifulSoup, Selenium, data extraction
    
- **Automation**: Form submission, browser interaction
    
- **OOP & Advanced Python**: Classes, inheritance, decorators, context managers, dunder methods
    
- **Data Handling**: Lists, dicts, sets, tuples, queues, stacks, linked lists
    
- **Algorithms & Complexity**: Sorting, searching, heaps, generators, Big-O notation
    
- **Production Concepts**: Logging, environment variables, authentication, Gunicorn/Uvicorn
    

---

## 📌 4. Mini Project Ideas

### 1️⃣ Weather Dashboard API

- Build with **Flask or FastAPI**
    
- Fetch weather data using `requests` from a public API
    
- Log each request & response with `logging`
    
- Optional: Serve multiple cities with query params
    

### 2️⃣ Job Scraper Automation

- Use **BeautifulSoup/Selenium** to scrape job listings
    
- Extract job title, company, location, and salary
    
- Save results in **CSV/JSON**
    
- Optionally serve results with a small Flask API endpoint
    

---

## 📌 5. Suggested Next Steps

- Start a **GitHub repository** for all mini projects
    
- Add **unit tests** (`pytest`/`unittest`)
    
- Try **Dockerizing** your APIs
    
- Explore **database integration**: SQLite, PostgreSQL, or MongoDB
    
- Deploy a small API on **Heroku** or **AWS**
    

---

This concludes the **2-month Python curriculum**, combining **core Python, advanced concepts, APIs, automation, and production readiness**.
