Python provides the **`os`** and **`sys`** modules to interact with the **operating system and runtime environment**. These are essential for file operations, environment variables, process info, and command-line interaction.

---

## 1️⃣ The `os` Module

The `os` module allows you to **interact with the filesystem and OS features**.

### 🔹 Get current working directory

```python
import os

cwd = os.getcwd()
print("Current directory:", cwd)
```

### 🔹 List files and directories

```python
print(os.listdir("."))  # list all files/folders in current directory
```

### 🔹 Create and remove directories

```python
os.mkdir("test_dir")  # create directory
os.makedirs("nested/dir", exist_ok=True)  # create nested directories
os.rmdir("test_dir")  # remove empty directory
```

### 🔹 Check file/directory existence

```python
print(os.path.exists("file.txt"))
print(os.path.isfile("file.txt"))
print(os.path.isdir("nested"))
```

### 🔹 Path operations

```python
print(os.path.join("folder", "file.txt"))  # folder/file.txt
print(os.path.basename("/home/user/file.txt"))  # file.txt
print(os.path.dirname("/home/user/file.txt"))   # /home/user
```

### 🔹 Environment variables

```python
print(os.environ.get("HOME"))  # prints user's home directory
os.environ["MY_VAR"] = "123"
print(os.environ["MY_VAR"])
```

---

## 2️⃣ The `sys` Module

The `sys` module gives access to **Python runtime environment and interpreter info**.

### 🔹 Command-line arguments

```python
import sys

print(sys.argv)  # list of command-line args, argv[0] is script name
# Run: python script.py arg1 arg2
```

### 🔹 Python version and platform

```python
print(sys.version)   # e.g., 3.10.12
print(sys.platform)  # e.g., linux, win32
```

### 🔹 Exiting and error codes

```python
# exit program with code
sys.exit(0)
# non-zero code indicates error
```

### 🔹 Standard input/output

```python
# writing to stdout
sys.stdout.write("Hello world\n")

# reading from stdin
# name = sys.stdin.readline().strip()
```

### 🔹 Path management

```python
print(sys.path)  # list of directories Python searches for modules
sys.path.append("/my/custom/modules")
```

---

## 3️⃣ Combined Example: File Checker Script

```python
import os, sys

if len(sys.argv) < 2:
    print("Usage: python file_checker.py <filename>")
    sys.exit(1)

filename = sys.argv[1]

if os.path.exists(filename):
    print(f"{filename} exists!")
    if os.path.isfile(filename):
        print(f"{filename} is a file.")
    elif os.path.isdir(filename):
        print(f"{filename} is a directory.")
else:
    print(f"{filename} does not exist.")
```

**Usage:**

```bash
python file_checker.py my_file.txt
```

---

## 4️⃣ Exercises

1. Write a script to list all `.py` files in the current directory.
    
2. Create a folder structure: `project/src`, `project/tests`. Check if the directories exist, create if not.
    
3. Print all environment variables.
    
4. Write a script that takes **filename as a command-line argument** and prints its **absolute path**.
    
5. Modify the file checker script to **rename the file** if it exists.
    

---

✅ By the end of **Day 20** → You’ll be comfortable **interacting with the OS, managing files/folders, environment variables, and command-line arguments**.

---
