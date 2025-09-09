
---

# 🗓️ 2-Month Python Plan

### 📌 Week 1: Getting Started + Control Structures & Data Types

- Python Intro, Setup, Syntax, Variables, Data Types
    
- Control Flow: if/else, loops, break/continue/pass
    
- Strings, Lists, Tuples, Sets, Dictionaries
    
- Comprehensions (`list`, `dict`, `set`)
    
- Mini project: Student Grade System / Simple ATM program
    

---

### 📌 Weeks 2 & 3: Functions & Modules

**Week 2 (Functions Core)**

- Defining functions, parameters, return values
    
- `*args`, `**kwargs`, default/keyword arguments
    
- Scope of variables (local, global, `nonlocal`)
    
- Lambda functions & higher-order functions
    
- Built-ins: `map`, `filter`, `zip`, `enumerate`
    
- Decorators (intro), Closures
    

**Week 3 (Modules Deep Dive)**

- Importing modules, `__name__ == "__main__"`
    
- Standard modules:
    
    - `math`, `random`, `datetime`
        
    - `collections` (`Counter`, `defaultdict`, `deque`, `namedtuple`, `OrderedDict`)
        
    - `functools` (`lru_cache`, `reduce`, `partial`, `wraps`)
        
    - `itertools` (`count`, `cycle`, `permutations`, `combinations`, `product`, `groupby`)
        
    - `os` & `sys` (files, directories, environment, arguments)
        
    - `re` (regex basics, patterns, groups, substitutions)
        
- Writing your own module & package
    

---

### 📌 Weeks 4 & 5: Data Structures, Memory & Complexity

**Week 4 (Data Handling)**

- JSON, CSV, XML, SQLite basics
    
- File handling (`open`, `with`, modes)
    
- Pickle for serialization
    
- Caching concepts (`functools.lru_cache`, custom cache dict)
    
- Big-O Notation (intro, examples with lists/dicts)
    

**Week 5 (Advanced Data Structures & Memory)**

- Logical Patterns (stack, queue, linked list with Python)
    
- High-Level Data Structures (heapq, bisect, priority queue)
    
- Memory management in Python (garbage collection, reference counting)
    
- Generators & Iterators (lazy evaluation, memory efficiency)
    
- Mini-project: Build a small caching system or implement a basic search index
    

---

### 📌 Week 6: OOPs & Advanced Python Concepts

- Classes, Objects, Attributes, Methods
    
- Encapsulation, Inheritance, Polymorphism
    
- `super()`, Method overriding
    
- Iterators & Generators (advanced)
    
- Decorators (deep dive) & Context Managers
    
- Virtual Environments & Packages
    
- Magic/Dunder Methods (`__str__`, `__len__`, etc.)
    

---

### 📌 Week 7: RESTful APIs + Automation

- Requests library (consuming APIs)
    
- Build APIs with Flask & FastAPI
    
- Production-ready API setup (uWSGI/Gunicorn basics)
    
- Selenium, BeautifulSoup, lxml for automation/scraping
    
- Logging & Error Handling
    

---

### 📌 Week 8: Pandas, NumPy & Best Practices

- Pandas basics: Series, DataFrames, GroupBy, Merge, Missing Data, Time Series
    
- NumPy basics: Ndarray, broadcasting, reshaping, random
    
- Visualization (`pandas.plot`, `matplotlib` intro)
    
- Unit Testing (`unittest`, `pytest`), Type Hints (`mypy`)
    
- Writing clean Python code (PEP8, SonarLint, Best Practices)
    
- Git & GitHub basics, CI/CD intro
    
   

---

# 🗓️ Week 1: Getting Started + Control Structures & Data Types

### 🎯 Goal of Week 1:

- Be comfortable with Python environment, syntax & style.
    
- Master conditionals, loops, operators.
    
- Work fluently with **strings, lists, tuples, sets, dicts, comprehensions**.
    
- End the week with a **mini project** to apply everything.
    

---

## 🔹 Day 1: Setup, Syntax, Variables & Data Types

- Install Python, VSCode / PyCharm / Jupyter
    
- Run Python from terminal, `.py` files, REPL
    
- **Basic Syntax**: indentation, comments, `print()`, input/output
    
- **Variables**: dynamic typing, naming rules
    
- **Data Types**: `int`, `float`, `str`, `bool`, `None`
    
- Type checking: `type()`, `isinstance()`
    
- Type conversion: `int("5")`, `float(10)`, `str(123)`
    

**Exercise:** Write a script that asks for name, age, and prints a greeting with age after 5 years.

---

## 🔹 Day 2: Operators & Expressions

- Arithmetic: `+ - * / // % **`
    
- Comparison: `== != > < >= <=`
    
- Logical: `and`, `or`, `not`
    
- Assignment: `= += -= *=`
    
- Membership: `in`, `not in`
    
- Identity: `is`, `is not`
    

**Exercise:** Build a simple calculator using `input()` and operators.

---

## 🔹 Day 3: Control Flow – if/else, nested conditions

- `if`, `elif`, `else`
    
- Nested conditions
    
- Short-hand if/else
    
- `and`/`or` in conditions
    

**Exercise:** Write a program to check if a number is positive/negative/zero. Then expand to also check if positive number is odd/even.

---

## 🔹 Day 4: Loops – while, for, break/continue/pass

- `while` loop, loop conditions
    
- `for` loop (range, iterables)
    
- Loop control: `break`, `continue`, `pass`
    
- Nested loops
    

**Exercise:** Write a program to generate multiplication table of a number using `for` loop.

---

## 🔹 Day 5: Strings

- Indexing & slicing: `"Hello"[0:3]`, `"Hello"[-1]`
    
- String methods: `.upper()`, `.lower()`, `.strip()`, `.replace()`, `.split()`, `.join()`
    
- f-strings & formatting
    
- Membership: `"py" in "python"`
    

**Exercise:** Count vowels in a string. Reverse a string without using slicing.

---

## 🔹 Day 6: Lists, Tuples, Sets, Dictionaries

- **Lists**: indexing, slicing, `.append()`, `.insert()`, `.remove()`, `.pop()`, `.sort()`
    
- **Tuples**: immutability, tuple unpacking
    
- **Sets**: uniqueness, `.add()`, `.remove()`, union, intersection, difference
    
- **Dictionaries**: key-value pairs, `.keys()`, `.values()`, `.items()`, iteration
    

**Exercise:**

- Make a dictionary of 3 students with names as keys and marks as values. Print topper’s name.
    
- Given a list with duplicates, remove duplicates using a set.
    

---

## 🔹 Day 7: Comprehensions + Recap + Mini Project

- **List Comprehension**: `[x**2 for x in range(10)]`
    
- **Dict Comprehension**: `{x: x**2 for x in range(5)}`
    
- **Set Comprehension**: `{x for x in "banana"}`
    
- Nested comprehensions
    

### Mini Project (choose one):

1. **Student Grade System**
    
    - Take student names & marks
        
    - Compute average
        
    - Assign grade A/B/C using conditions
        
    - Store results in dict
        
2. **ATM Simulation**
    
    - Initial balance
        
    - Menu: deposit, withdraw, check balance
        
    - Use loops & conditionals
        

---

✅ By end of Week 1:

- You’ll have strong basics.
    
- You’ll already be solving real problems with **flow + collections**.
    
- You’ll be ready to deep dive into **Functions & Modules** from Week 2.
    

---

# 🗓️ Week 2: Functions Core

### 🎯 Goal of Week 2:

- Understand how to write, call, and structure functions.
    
- Learn parameter types (`positional`, `default`, `*args`, `**kwargs`).
    
- Grasp variable scope (`local`, `global`, `nonlocal`).
    
- Use **lambda functions** and **higher-order functions** (`map`, `filter`, `zip`, `enumerate`).
    
- Intro to **decorators** and **closures**.
    

---

## 🔹 Day 8: Functions – Definition & Return Values

- Defining & calling functions
    

```python
def greet(name):
    return f"Hello {name}!"

print(greet("Alice"))
```

- `return` vs printing
    
- Multiple return values (tuple return)
    

```python
def calc(a, b):
    return a+b, a-b
print(calc(5, 3))  # (8, 2)
```

**Exercise:** Write a function to check if a number is prime.

---

## 🔹 Day 9: Function Parameters

- Positional arguments
    
- Default arguments
    

```python
def greet(name="Guest"):
    print(f"Hello {name}")
```

- Keyword arguments
    

```python
def introduce(name, age):
    print(f"{name} is {age} years old")

introduce(age=25, name="Bob")
```

**Exercise:** Write a function `power(base, exp=2)` that computes exponentiation, defaulting to square.

---

## 🔹 Day 10: `*args` & `**kwargs` (Variable-Length Arguments)

- `*args` for multiple positional arguments
    

```python
def add_all(*nums):
    return sum(nums)

print(add_all(1,2,3,4))
```

- `**kwargs` for key-value arguments
    

```python
def show_details(**info):
    for k,v in info.items():
        print(f"{k}: {v}")

show_details(name="Alice", age=25, city="NY")
```

**Exercise:** Write a function `describe_person(name, *hobbies, **details)` that prints hobbies and details.

---

## 🔹 Day 11: Variable Scope – local, global, nonlocal

- Local vs global variables
    

```python
x = 10
def func():
    x = 5  # local
    print(x)
func()
print(x)
```

- `global` keyword
    

```python
x = 10
def change():
    global x
    x = 20
```

- `nonlocal` in nested functions
    

```python
def outer():
    x = "outer"
    def inner():
        nonlocal x
        x = "inner"
    inner()
    print(x)
outer()
```

**Exercise:** Write a nested function where the inner function modifies a variable of the outer function using `nonlocal`.

---

## 🔹 Day 12: Lambda Functions

- Anonymous functions
    

```python
square = lambda x: x**2
print(square(5))
```

- With `map`, `filter`
    

```python
nums = [1,2,3,4,5]
squares = list(map(lambda x: x**2, nums))
evens = list(filter(lambda x: x%2==0, nums))
```

**Exercise:** Use `map` and `filter` with lambda to generate cubes of even numbers from 1–10.

---

## 🔹 Day 13: Built-in Higher Order Functions

- `map()`, `filter()` (review)
    
- `zip()`
    

```python
names = ["Alice", "Bob"]
scores = [85, 90]
print(list(zip(names, scores)))
```

- `enumerate()`
    

```python
for i, val in enumerate(["a","b","c"], start=1):
    print(i, val)
```

- `sorted()` with `key`
    

```python
words = ["apple","banana","cherry"]
print(sorted(words, key=len))
```

**Exercise:** Given a list of `(name, age)`, sort by age using `sorted()` with `lambda`.

---

## 🔹 Day 14: Closures & Intro to Decorators

- **Closure** (function inside function that remembers outer scope)
    

```python
def make_multiplier(n):
    def multiplier(x):
        return x * n
    return multiplier

double = make_multiplier(2)
print(double(5))  # 10
```

- **Decorator basics** (wrap one function with another)
    

```python
def my_decorator(func):
    def wrapper():
        print("Before")
        func()
        print("After")
    return wrapper

@my_decorator
def say_hello():
    print("Hello")

say_hello()
```

**Exercise:** Write a decorator that logs `"Function started"` and `"Function ended"` around any function call.

---

## 🔹 Day 15: Week Recap + Mini Project

👉 Combine **functions + arguments + lambda + decorators**.

### Mini Project Ideas:

1. **Calculator (with decorator logging)**
    
    - Functions: add, subtract, multiply, divide
        
    - Decorator: log every operation
        
    - Use `*args` to allow multiple inputs
        
2. **Student Score Manager**
    
    - Function to add students with marks
        
    - Function to compute average, highest, lowest
        
    - Use `zip()` to pair names and scores
        
    - Use `lambda` + `sorted()` to rank students
        

---

✅ By end of Week 2:

- You’ll know **functions inside-out**.
    
- Be confident with **scopes, lambdas, built-ins**.
    
- Be ready for **Week 3: Modules Deep Dive** (where we explore `collections`, `functools`, `itertools`, `os`, `sys`, `re`).
      

---

# 🗓️ Week 3: Modules Deep Dive

### 🎯 Goal of Week 3

- Learn how to import and organize modules.
    
- Get hands-on with **utility modules** (`math`, `random`, `datetime`).
    
- Master **data handling & functional tools** (`collections`, `functools`, `itertools`).
    
- Work with **system-level modules** (`os`, `sys`).
    
- Get strong with **regex (`re`)** for pattern matching.
    

---

## 🔹 Day 16: Importing Modules & Standard Utilities

- Different ways of importing
    

```python
import math
from math import sqrt
import math as m
```

- **math** module
    

```python
import math
print(math.sqrt(16))   # 4.0
print(math.pi)         # 3.14159
print(math.factorial(5)) # 120
```

- **random** module
    

```python
import random
print(random.randint(1,10))
print(random.choice(["red","green","blue"]))
```

- **datetime** module
    

```python
from datetime import datetime
now = datetime.now()
print(now.strftime("%Y-%m-%d %H:%M:%S"))
```

**Exercise:** Write a program to simulate a dice roll until you get a 6.

---

## 🔹 Day 17: `collections` – Advanced Data Structures

- `Counter`
    

```python
from collections import Counter
print(Counter("banana"))
```

- `defaultdict`
    

```python
from collections import defaultdict
dd = defaultdict(int)
dd["a"] += 1
print(dd)
```

- `deque` (fast queue)
    

```python
from collections import deque
d = deque([1,2,3])
d.appendleft(0)
d.pop()
print(d)
```

- `namedtuple`
    

```python
from collections import namedtuple
Point = namedtuple("Point", "x y")
p = Point(10,20)
print(p.x, p.y)
```

- `OrderedDict` (preserves insertion order – default since Python 3.7, but still useful).
    

**Exercise:** Use `Counter` to find top 3 most common words in a sentence.

---

## 🔹 Day 18: `functools` – Functional Programming Helpers

- `reduce()`
    

```python
from functools import reduce
nums = [1,2,3,4]
print(reduce(lambda x,y: x+y, nums))
```

- `partial()`
    

```python
from functools import partial
def power(base, exp):
    return base**exp

square = partial(power, exp=2)
print(square(5))
```

- `lru_cache()` for memoization
    

```python
from functools import lru_cache
@lru_cache(maxsize=None)
def fib(n):
    if n<2: return n
    return fib(n-1)+fib(n-2)
print(fib(50))
```

- `wraps` in decorators (to preserve function metadata).
    

**Exercise:** Write a recursive factorial function and use `lru_cache` to speed it up.

---

## 🔹 Day 19: `itertools` – Infinite & Combinatorial Tools

- Infinite iterators: `count`, `cycle`, `repeat`
    

```python
from itertools import count, cycle, repeat
for i in count(5,2):
    if i>15: break
    print(i)
```

- Combinatorics: `permutations`, `combinations`, `product`
    

```python
from itertools import permutations, combinations
print(list(permutations([1,2,3], 2)))
print(list(combinations([1,2,3], 2)))
```

- Grouping: `groupby`
    

```python
from itertools import groupby
nums = [1,1,2,2,3,3,3]
for k, g in groupby(nums):
    print(k, list(g))
```

**Exercise:** Generate all possible 3-letter words using letters `a,b,c`.

---

## 🔹 Day 20: `os` & `sys` – System Utilities

- `os` module
    

```python
import os
print(os.getcwd())     # current directory
os.mkdir("test_dir")
os.rmdir("test_dir")
print(os.listdir("."))
```

- File operations with `os.path`
    

```python
print(os.path.exists("myfile.txt"))
print(os.path.join("folder","file.txt"))
```

- `sys` module
    

```python
import sys
print(sys.version)
print(sys.argv)   # command line args
```

**Exercise:** Write a script that accepts a filename from command line (`sys.argv`) and prints line count.

---

## 🔹 Day 21: `re` – Regular Expressions

- Matching patterns
    

```python
import re
print(re.match(r"Hello", "Hello World"))
```

- Searching & finding
    

```python
text = "My phone is 123-456-7890"
match = re.search(r"\d{3}-\d{3}-\d{4}", text)
print(match.group())
```

- Splitting & replacing
    

```python
print(re.split(r"\s+", "one two   three"))
print(re.sub(r"\d", "*", "abc123"))
```

- Groups & capture
    

```python
m = re.match(r"(\d+)-(\d+)", "123-456")
print(m.groups())  # ('123','456')
```

**Exercise:** Write regex to validate an email address.

---

## 🔹 Day 22: Writing Your Own Module & Package

- Create `mymath.py`
    

```python
def add(a,b): return a+b
def sub(a,b): return a-b
```

- Import in another file
    

```python
import mymath
print(mymath.add(5,3))
```

- Packages with `__init__.py`
    

```bash
mypackage/
    __init__.py
    module1.py
    module2.py
```

- `__name__ == "__main__"` usage.
    

**Exercise:** Create a package `geometry` with modules `circle.py` and `rectangle.py`. Import and calculate area.

---

## 🔹 Day 23: Week Recap + Mini Project

👉 Combine modules to solve a **real-world problem**.

### Mini Project Ideas

1. **Log Analyzer**
    
    - Use `os` to read all `.log` files in a folder
        
    - Use `re` to extract IP addresses & timestamps
        
    - Use `collections.Counter` to find most frequent IPs
        
2. **Password Generator**
    
    - Use `random` + `string` to generate strong passwords
        
    - Allow user to specify length and character types
        
3. **Student Report**
    
    - Read CSV file of students with scores (`csv` or `pandas` optional)
        
    - Use `functools.reduce` to compute totals
        
    - Use `sorted()` with `lambda` to rank students
        

---

✅ By end of Week 3:

- You’ll be **very comfortable with Python’s standard modules**.
    
- You’ll know how to leverage `collections`, `functools`, `itertools`, `os`, `sys`, `re`.
    
- You’ll be ready to dive into **Week 4: Data Structures, Memory & Complexity** (expanded).
    

---

# 🗓️ Week 4: Data Structures, Memory & Complexity (Part 1)

### 🎯 Goal of Week 4

- Understand **built-in data structures** (list, tuple, dict, set).
    
- Learn about **custom data structures with classes**.
    
- Explore **stacks, queues, linked lists**.
    
- Begin analyzing code with **Big-O complexity**.
    
- Understand **Python’s memory model & garbage collection basics**.
    

---

## 🔹 Day 24: Lists & Tuples – Deep Dive

- Lists
    
    - Mutable, dynamic, ordered
        
    - Common operations: append, extend, insert, pop, remove, sort, slicing
        
    
    ```python
    nums = [1,2,3]
    nums.append(4)
    nums.remove(2)
    nums.sort()
    print(nums)
    ```
    
- Tuples
    
    - Immutable, faster than lists
        
    - Packing/unpacking
        
    
    ```python
    tup = (10,20,30)
    a,b,c = tup
    print(a,b,c)
    ```
    
- Nested structures (list of lists, tuple of tuples).
    
- When to use list vs tuple.
    

**Exercise:** Implement a function to rotate a list by `k` positions.

---

## 🔹 Day 25: Dictionaries & Sets

- Dictionaries
    
    - Key-value store, fast lookup
        
    - Methods: `.get()`, `.keys()`, `.values()`, `.items()`
        
    
    ```python
    student = {"name":"Alice","age":21}
    print(student.get("name"))
    ```
    
- Sets
    
    - Unique, unordered
        
    - Operations: union, intersection, difference
        
    
    ```python
    a={1,2,3}; b={3,4,5}
    print(a & b)  # intersection
    ```
    
- `frozenset` (immutable set).
    
- Dict vs Set vs List performance.
    

**Exercise:** Find all unique words from a paragraph and their frequencies.

---

## 🔹 Day 26: Stack & Queue (Abstract Data Structures)

- Stack (LIFO)
    
    ```python
    stack = []
    stack.append(1)
    stack.append(2)
    print(stack.pop())
    ```
    
- Queue (FIFO)
    
    ```python
    from collections import deque
    q = deque([1,2])
    q.append(3)
    print(q.popleft())
    ```
    
- Applications: Undo/Redo, Task Scheduling.
    

**Exercise:** Implement a browser history using stack.

---

## 🔹 Day 27: Linked List Implementation

- Node class
    
    ```python
    class Node:
        def __init__(self, data):
            self.data = data
            self.next = None
    ```
    
- Singly Linked List
    
    - Insert at beginning
        
    - Insert at end
        
    - Traverse
        
- Doubly Linked List (optional for advanced practice).
    

**Exercise:** Create a linked list of numbers and write a function to reverse it.

---

## 🔹 Day 28: Recap of Built-In vs Custom Data Structures

- Compare Lists, Tuples, Dicts, Sets, Stacks, Queues, Linked Lists.
    
- Performance considerations (when to use what).
    
- Mini coding drills:
    
    - Reverse a string using stack
        
    - Check for balanced parentheses using stack
        
    - Implement queue using two stacks
        

---

## 🔹 Day 29: Time Complexity – Big-O Notation (Intro)

- Concept of algorithmic complexity
    
- Common complexities:
    
    - O(1) → Constant time
        
    - O(log n) → Binary search
        
    - O(n) → Linear search
        
    - O(n log n) → Sorting
        
    - O(n²) → Nested loops
        
- Example: Searching in list vs dictionary
    
    ```python
    nums = list(range(1000000))
    print(999999 in nums)  # O(n)
    
    d = {x: True for x in range(1000000)}
    print(999999 in d)     # O(1)
    ```
    

**Exercise:** Compare performance of list lookup vs set lookup for large datasets.

---

## 🔹 Day 30: Memory Management & Garbage Collection Basics

- Python Memory Model
    
    - Objects stored in **heap**
        
    - Variables are references
        
- Reference Counting
    
    ```python
    import sys
    a = [1,2,3]
    b = a
    print(sys.getrefcount(a))  # references count
    ```
    
- Garbage Collection
    
    - Circular references
        
    - `gc` module
        
    
    ```python
    import gc
    print(gc.get_threshold())
    ```
    
- `del` keyword and object lifecycle.
    

**Exercise:** Write a program that creates circular references and observe garbage collection.

---

## 🔹 Day 31: Week Recap + Mini Project

👉 Apply concepts to build something that uses **data structures + complexity awareness**.

### Mini Project Ideas

1. **Text Analyzer**
    
    - Read text file
        
    - Use dict to count word frequency
        
    - Use set to find unique words
        
    - Sort by frequency (complexity analysis)
        
2. **Task Manager**
    
    - Use queue for pending tasks
        
    - Use stack for recently completed tasks
        
    - Show complexity difference for operations
        
3. **Linked List Playground**
    
    - Implement linked list
        
    - Add insert, delete, reverse
        
    - Compare performance with list
        

---

✅ By the end of **Week 4**:

- You’ll have **strong foundation in data structures**.
    
- You’ll understand **time complexity basics**.
    
- You’ll know how Python manages memory.
    

---

# 🗓️ Week 5: Data Structures, Memory & Complexity (Part 2)

### 🎯 Goal of Week 5

- Learn **advanced data structures** beyond lists & dicts.
    
- Implement **sorting & searching algorithms** in Python.
    
- Use **heapq, bisect, priority queues**.
    
- Deep dive into **generators, iterators, and lazy evaluation**.
    
- Apply **complexity analysis** with real-world coding drills.
    

---

## 🔹 Day 32: Sorting Algorithms – Basics & Complexity

- Built-in Sorting
    
    ```python
    nums = [5,2,9,1]
    print(sorted(nums))   # new list
    nums.sort()           # in-place
    ```
    
- Custom sorting with `key`
    
    ```python
    words = ["apple","banana","pear"]
    print(sorted(words, key=len))
    ```
    
- Bubble Sort (O(n²)) – concept & implementation
    
- Insertion Sort (O(n²)) – concept & implementation
    
- Python’s `Timsort` (hybrid sort → O(n log n))
    

**Exercise:** Write your own bubble sort and compare with Python’s `sort()` on large input.

---

## 🔹 Day 33: Searching Algorithms

- Linear Search (O(n))
    
- Binary Search (O(log n))
    
    ```python
    import bisect
    nums = [1,3,4,7,10]
    pos = bisect.bisect_left(nums, 7)
    print("Found at index:", pos)
    ```
    
- `bisect` module (binary search helper).
    
- Hash-based search (dict, set lookups O(1)).
    

**Exercise:** Implement binary search recursively.

---

## 🔹 Day 34: Heaps & Priority Queues

- `heapq` module
    
    - Min heap (default)
        
    - Max heap (invert values)
        
    
    ```python
    import heapq
    nums = [5,1,8,2]
    heapq.heapify(nums)
    print(heapq.heappop(nums))  # smallest
    ```
    
- Use cases: Dijkstra’s algorithm, task scheduling.
    
- Priority Queue with `queue.PriorityQueue`.
    

**Exercise:** Find the top 3 largest elements from a list using `heapq`.

---

## 🔹 Day 35: Iterators & Generators

- Iterator protocol (`__iter__`, `__next__`)
    
- Generator functions with `yield`
    
    ```python
    def countdown(n):
        while n > 0:
            yield n
            n -= 1
    for x in countdown(5):
        print(x)
    ```
    
- Generator expressions
    
- `itertools` for infinite iterators (`count`, `cycle`)
    
- Memory efficiency: list vs generator
    

**Exercise:** Implement Fibonacci sequence with a generator.

---

## 🔹 Day 36: Memory Efficiency & Lazy Evaluation

- Lists vs Generators memory usage (`sys.getsizeof`)
    
- Example: reading a 1GB file line by line with generator
    
    ```python
    def read_file(path):
        with open(path) as f:
            for line in f:
                yield line
    ```
    
- `range` vs `xrange` in Python 2 (concept of lazy evaluation)
    
- When to use generators to save memory
    

**Exercise:** Compare memory usage of storing 1 million numbers in a list vs a generator.

---

## 🔹 Day 37: Complexity Analysis in Practice

- Compare performance of:
    
    - Linear search vs binary search
        
    - List append vs insert at index 0
        
    - Dict lookup vs list lookup
        
- Time measurement with `time` & `timeit`
    
    ```python
    import timeit
    print(timeit.timeit("1000000 in range(10000000)", number=10))
    ```
    

**Exercise:** Write code to test performance of different search algorithms on large inputs.

---

## 🔹 Day 38: Week Recap + Mini Project

👉 Consolidate concepts of **sorting, searching, heaps, generators, and complexity**.

### Mini Project Ideas

1. **Event Scheduler**
    
    - Use heap/priority queue to manage upcoming events.
        
    - Insert/remove events based on time.
        
    - Efficient lookup with dict.
        
2. **Search Engine Toy**
    
    - Store words from text file in dict.
        
    - Search words using binary search vs dict lookup.
        
    - Compare performance.
        
3. **Data Stream Processor**
    
    - Use generator to process a huge CSV lazily.
        
    - Calculate rolling averages with limited memory.
        

---

✅ By the end of **Week 5**:

- You’ll know **sorting, searching, heaps, and queues**.
    
- You’ll be comfortable with **iterators, generators, and lazy evaluation**.
    
- You’ll have hands-on practice with **complexity measurement**.
    

---

# 🗓️ Week 6: OOP & Advanced Python Concepts

### 🎯 Goal of Week 6

- Learn OOP basics: **Classes, Objects, Methods, Attributes**
    
- Understand **Encapsulation, Inheritance, Polymorphism**
    
- Use **special/dunder methods** to customize class behavior
    
- Explore **decorators, context managers, and advanced features**
    
- Build practical OOP mini-projects
    

---

## 🔹 Day 39: Introduction to Classes & Objects

- What is OOP? Why use it?
    
- Define a class & create objects
    
    ```python
    class Car:
        def __init__(self, brand, model):
            self.brand = brand
            self.model = model
    
        def drive(self):
            print(f"{self.brand} {self.model} is driving")
    
    car1 = Car("Tesla", "Model 3")
    car1.drive()
    ```
    
- Instance variables vs class variables
    
- `__init__` method (constructor)
    

**Exercise:** Create a `Book` class with title, author, and method `get_info()`.

---

## 🔹 Day 40: Encapsulation & Access Modifiers

- Public, Protected (`_var`), Private (`__var`)
    
- Getter & Setter methods
    
    ```python
    class BankAccount:
        def __init__(self, balance=0):
            self.__balance = balance
    
        def deposit(self, amount):
            self.__balance += amount
    
        def get_balance(self):
            return self.__balance
    ```
    
- Why encapsulation is important (data security, controlled access)
    

**Exercise:** Implement a `Student` class with private `marks`, add getter & setter.

---

## 🔹 Day 41: Inheritance

- Single Inheritance
    
    ```python
    class Animal:
        def speak(self):
            print("Animal speaks")
    
    class Dog(Animal):
        def speak(self):
            print("Woof!")
    ```
    
- Multiple Inheritance
    
- Multilevel Inheritance
    
- `super()` keyword
    

**Exercise:** Create a `Vehicle` class → `Car` → `ElectricCar` with method overriding.

---

## 🔹 Day 42: Polymorphism & Method Overriding

- Concept of Polymorphism (many forms)
    
- Duck typing in Python
    
    ```python
    class Bird:
        def fly(self): print("Flies")
    
    class Airplane:
        def fly(self): print("Airplane flies")
    
    for obj in [Bird(), Airplane()]:
        obj.fly()
    ```
    
- Operator overloading using dunder methods
    
    ```python
    class Vector:
        def __init__(self, x, y): self.x, self.y = x, y
        def __add__(self, other): return Vector(self.x+other.x, self.y+other.y)
    ```
    

**Exercise:** Implement a `Vector` class with `+` and `-` operator overloading.

---

## 🔹 Day 43: Dunder (Magic) Methods & Advanced OOP

- `__str__`, `__repr__`
    
- `__len__`, `__eq__`, `__lt__` (comparison)
    
- `__getitem__`, `__setitem__`
    
- Example:
    
    ```python
    class MyList:
        def __init__(self, data): self.data = data
        def __len__(self): return len(self.data)
        def __getitem__(self, idx): return self.data[idx]
    ```
    
- How Python uses these behind the scenes.
    

**Exercise:** Build a custom `ShoppingCart` class that behaves like a list.

---

## 🔹 Day 44: Iterators, Generators & Decorators in OOP

- Making classes iterable (`__iter__`, `__next__`)
    
- Generators inside classes
    
- Function decorators (`@staticmethod`, `@classmethod`)
    
- Custom decorators
    
    ```python
    def log(func):
        def wrapper(*a, **kw):
            print("Calling", func.__name__)
            return func(*a, **kw)
        return wrapper
    
    @log
    def greet(): print("Hello")
    ```
    

**Exercise:** Create a decorator that measures execution time of methods.

---

## 🔹 Day 45: Context Managers & Advanced Features

- `with` statement and `__enter__`, `__exit__`
    
    ```python
    class FileOpener:
        def __init__(self, filename): self.filename = filename
        def __enter__(self): self.file = open(self.filename, "r"); return self.file
        def __exit__(self, exc_type, exc_val, exc_tb): self.file.close()
    ```
    
- Using `contextlib` (`contextmanager`)
    
- Abstract Base Classes (`abc` module)
    

**Exercise:** Create a context manager that times how long a block of code runs.

---

## 🔹 Day 46: Week Recap + Mini Project

👉 Apply **OOP + Advanced Features** in practice.

### Mini Project Ideas

1. **Library Management System**
    
    - Classes: `Book`, `Member`, `Library`
        
    - Borrow/Return books with encapsulation
        
    - Use inheritance for different member types
        
2. **Banking System**
    
    - Classes: `Account`, `SavingsAccount`, `CheckingAccount`
        
    - Encapsulation for balance
        
    - Method overriding for withdrawals
        
3. **E-commerce Cart**
    
    - `Product`, `Cart`, `Order`
        
    - Use dunder methods for cart operations
        
    - Add a context manager for managing order transactions
        

---

✅ By the end of **Week 6**:

- You’ll master **OOP in Python**.
    
- You’ll know **encapsulation, inheritance, polymorphism**.
    
- You’ll be comfortable with **dunder methods, decorators, and context managers**.
    

---

# 🗓️ Week 7: RESTful APIs + Automation

### 🎯 Goal of Week 7

- Learn how to **send HTTP requests** and handle responses
    
- Build your own **REST APIs** using Flask and FastAPI
    
- Understand **API request parameters, headers, error handling**
    
- Learn **automation tools**: web scraping & browser automation
    
- Apply **logging & debugging** in real projects
    

---

## 🔹 Day 47: Consuming REST APIs with Python

- HTTP basics: GET, POST, PUT, DELETE
    
- `requests` module
    
    ```python
    import requests
    r = requests.get("https://jsonplaceholder.typicode.com/posts/1")
    print(r.json())
    ```
    
- Sending query params & headers
    
    ```python
    r = requests.get("https://api.github.com/search/repositories",
                     params={"q": "python"})
    ```
    
- Handling errors: `status_code`, `raise_for_status()`
    

**Exercise:** Use a public API (e.g., OpenWeatherMap) to fetch and display weather data.

---

## 🔹 Day 48: Building APIs with Flask (Part 1)

- Flask setup & first app
    
    ```python
    from flask import Flask
    app = Flask(__name__)
    
    @app.route("/")
    def home():
        return {"message": "Hello API"}
    
    if __name__ == "__main__":
        app.run(debug=True)
    ```
    
- Defining routes (`GET`, `POST`)
    
- JSON request/response
    
- Handling path & query parameters
    

**Exercise:** Build a simple Flask API that returns student info by ID.

---

## 🔹 Day 49: Building APIs with Flask (Part 2)

- Structuring a Flask app (blueprints, config)
    
- Request validation
    
- Error handling & HTTP status codes
    
    ```python
    from flask import jsonify
    @app.errorhandler(404)
    def not_found(e):
        return jsonify(error="Resource not found"), 404
    ```
    
- Middleware basics
    
- Postman/Insomnia for testing APIs
    

**Exercise:** Extend your student API with error handling & validation.

---

## 🔹 Day 50: FastAPI – Modern Python APIs

- FastAPI setup
    
    ```python
    from fastapi import FastAPI
    app = FastAPI()
    
    @app.get("/")
    def home():
        return {"msg": "Hello FastAPI"}
    ```
    
- Automatic Swagger UI (`/docs`)
    
- Request body validation with Pydantic
    
- Async endpoints (`async def`)
    

**Exercise:** Build a FastAPI app for managing tasks (CRUD: Create, Read, Update, Delete).

---

## 🔹 Day 51: Production-Ready APIs

- Running with Gunicorn / Uvicorn
    
- Environment variables (`python-dotenv`)
    
- Logging & monitoring (`logging` module)
    
- API authentication basics (API keys, JWT intro)
    
- Best practices for structuring production apps
    

**Exercise:** Containerize your API with Docker (optional if interested).

---

## 🔹 Day 52: Web Scraping with BeautifulSoup & Automation with Selenium

- **BeautifulSoup**
    
    ```python
    from bs4 import BeautifulSoup
    import requests
    r = requests.get("https://example.com")
    soup = BeautifulSoup(r.text, "html.parser")
    print(soup.title.string)
    ```
    
- Parsing HTML tables, extracting links
    
- **Selenium**
    
    - Launch browser
        
    - Locate elements (`find_element`)
        
    - Automate clicks, form submission
        

**Exercise:** Scrape product prices from an e-commerce site & save them to CSV.

---

## 🔹 Day 53: Logging, Debugging & Final Recap

- Logging levels: DEBUG, INFO, WARNING, ERROR, CRITICAL
    
- Configuring log format & file handling
    
    ```python
    import logging
    logging.basicConfig(filename="app.log", level=logging.INFO)
    logging.info("App started")
    ```
    
- Debugging with `pdb`
    
- Recap: Consuming APIs, Flask, FastAPI, Scraping, Automation
    

**Mini Project Ideas:**

1. **Weather Dashboard API**
    
    - Flask/FastAPI API that fetches weather info using `requests`
        
    - Logs each request & response
        
2. **Job Scraper Automation**
    
    - Use BeautifulSoup/Selenium to scrape jobs from a site
        
    - Save results to CSV/JSON
        
    - Serve results with Flask API
        

---

✅ By the end of **Week 7**:

- You’ll be able to **consume and build REST APIs**.
    
- You’ll know how to make an API **production ready**.
    
- You’ll have skills in **web scraping & automation**.
    
- You’ll understand **logging & debugging for real-world projects**.
    


---

# 🗓️ Week 8: Pandas, NumPy & Best Practices

### 🎯 Goal of Week 8

- Learn how to **analyze and manipulate data** with Pandas
    
- Perform **fast numerical computations** with NumPy
    
- Visualize data using Pandas/Matplotlib
    
- Practice **testing, typing, debugging, and clean code principles**
    
- Understand **Git basics and CI/CD pipelines**
    

---

## 🔹 Day 54: Pandas – Series & DataFrames

- What is Pandas? Why use it?
    
- Series (1D labeled array)
    
    ```python
    import pandas as pd
    s = pd.Series([10, 20, 30], index=["a", "b", "c"])
    print(s["b"])
    ```
    
- DataFrame (2D labeled table)
    
    ```python
    data = {"name": ["Alice","Bob"], "age": [25,30]}
    df = pd.DataFrame(data)
    print(df.head())
    ```
    
- Reading & writing files (`csv`, `excel`, `json`)
    

**Exercise:** Read a CSV file of sales data and display top 5 rows.

---

## 🔹 Day 55: Pandas – Data Operations

- Indexing, slicing, filtering
    
- Conditional selection
    
    ```python
    df[df["age"] > 25]
    ```
    
- Adding/removing columns
    
- Handling missing values (`dropna`, `fillna`)
    
- Aggregations (`sum`, `mean`, `value_counts`)
    

**Exercise:** Clean a dataset with missing values and compute average values.

---

## 🔹 Day 56: Pandas – Grouping, Merging & Time Series

- GroupBy & aggregation
    
    ```python
    df.groupby("department")["salary"].mean()
    ```
    
- Merging, joining, concatenation
    
- Sorting & ranking
    
- Working with dates (`pd.to_datetime`, resampling)
    

**Exercise:** Analyze employee dataset: average salary by department & year.

---

## 🔹 Day 57: NumPy Basics

- NumPy arrays vs Python lists (performance)
    
- Creating arrays (`np.array`, `np.zeros`, `np.arange`, `np.linspace`)
    
- Indexing, slicing, reshaping
    
    ```python
    import numpy as np
    arr = np.arange(1,10).reshape(3,3)
    print(arr[0,1])
    ```
    
- Element-wise operations
    
- Broadcasting
    

**Exercise:** Create a 5x5 NumPy array and compute row/column sums.

---

## 🔹 Day 58: NumPy – Advanced Operations

- Mathematical functions (`sin`, `exp`, `sqrt`)
    
- Random number generation (`np.random`)
    
- Concatenation, splitting
    
- Linear algebra basics (`dot`, `matrix multiplication`)
    

**Exercise:** Simulate dice rolls (1000 times) and compute probability distribution.

---

## 🔹 Day 59: Visualization & Analysis Project

- Pandas plotting (`df.plot()`)
    
- Matplotlib basics
    
- Mini Data Analysis Project:
    
    - Load dataset (CSV)
        
    - Clean missing values
        
    - Group & aggregate
        
    - Plot trends
        

**Exercise:** Analyze COVID-19 dataset (cases by country, trend line plot).

---

## 🔹 Day 60: Best Practices – Testing, Typing, Git & CI/CD

- Unit testing with `unittest` & `pytest`
    
    ```python
    def add(x,y): return x+y
    def test_add(): assert add(2,3)==5
    ```
    
- Type hints & static analysis (`mypy`)
    
    ```python
    def greet(name: str) -> str:
        return "Hello " + name
    ```
    
- Logging & debugging recap
    
- Writing clean code (PEP8, SonarLint)
    
- Git & GitHub basics
    
- CI/CD pipelines introduction (GitHub Actions, GitLab CI)
    

**Mini Project (Capstone):**

- End-to-end project combining all skills:
    
    - Scrape data → Clean with Pandas → Store in CSV → Build REST API to serve data → Add logging & unit tests
        

---

✅ By the end of **Week 8** (and the 2 months total):

- You’ll be able to **analyze data with Pandas & NumPy**.
    
- You’ll know how to **build reliable APIs & automation scripts**.
    
- You’ll understand **testing, debugging, version control, and CI/CD**.
    
- You’ll have a **portfolio of mini-projects** to showcase.
    

---
