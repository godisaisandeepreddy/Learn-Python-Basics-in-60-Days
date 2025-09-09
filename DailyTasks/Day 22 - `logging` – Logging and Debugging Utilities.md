
The `logging` module in Python is used to **track events that happen while a program runs**.  
It is more flexible than using `print()` because you can set **levels, formats, and destinations**.

---

## 1️⃣ Why Use Logging?

- Helps **debug code** without stopping execution.
    
- Provides **different severity levels**.
    
- Can **write logs to files** for monitoring production applications.
    

---

## 2️⃣ Logging Levels

|Level|Description|Numeric Value|
|---|---|---|
|DEBUG|Detailed information, useful for diagnosing problems|10|
|INFO|Confirmation that things are working as expected|20|
|WARNING|Something unexpected happened, but program continues|30|
|ERROR|Serious problem, program might fail|40|
|CRITICAL|Very serious error, program may terminate|50|

---

## 3️⃣ Basic Logging

```python
import logging

# Basic configuration
logging.basicConfig(level=logging.DEBUG)

logging.debug("Debug message")
logging.info("Info message")
logging.warning("Warning message")
logging.error("Error message")
logging.critical("Critical message")
```

✅ Output goes to **console** by default.

---

## 4️⃣ Logging to a File

```python
import logging

logging.basicConfig(filename="app.log",
                    filemode="w",  # overwrite each time
                    format="%(asctime)s - %(levelname)s - %(message)s",
                    level=logging.INFO)

logging.info("Application started")
logging.warning("This is a warning")
logging.error("An error occurred")
```

- Logs are now written to `app.log` with **timestamps and levels**.
    

---

## 5️⃣ Advanced Logging

### 🔹 Custom Logger

```python
import logging

logger = logging.getLogger("MyLogger")
logger.setLevel(logging.DEBUG)

# Console Handler
ch = logging.StreamHandler()
ch.setLevel(logging.INFO)

# File Handler
fh = logging.FileHandler("myapp.log")
fh.setLevel(logging.ERROR)

# Formatter
formatter = logging.Formatter("%(name)s - %(levelname)s - %(message)s")
ch.setFormatter(formatter)
fh.setFormatter(formatter)

# Add handlers to logger
logger.addHandler(ch)
logger.addHandler(fh)

logger.debug("Debug message")   # not shown (level INFO)
logger.info("Info message")     # shown in console
logger.error("Error message")   # shown in console & file
```

---

## 6️⃣ Using Logging in Functions

```python
import logging

logging.basicConfig(level=logging.INFO)

def divide(a, b):
    try:
        return a / b
    except ZeroDivisionError:
        logging.error("Division by zero attempted")
        return None

divide(10, 0)
```

✅ Output: `ERROR:root:Division by zero attempted`

---

## 7️⃣ Exercises

1. Configure a logger to write **all levels** to `debug.log` and **errors only** to `error.log`.
    
2. Write a function that reads numbers from a list and logs **INFO** for each successful read, and **WARNING** if number is negative.
    
3. Modify a mini-project (e.g., Calculator) to log all operations performed with **timestamp and operands**.
    
4. Try logging **custom messages** with different formats using `Formatter`.
    

---

✅ By the end of **Day 22** → You’ll be able to **track program execution, debug issues efficiently, and maintain logs for monitoring**.

---

