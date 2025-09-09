
---

## Recap of week’s core topics (bullet summary)

- Function definitions, return values (Day 8).
    
- Parameters: positional, default, keyword (Day 9).
    
- Variable-length args: `*args`, `**kwargs` and unpacking (Day 10).
    
- Scopes: local, global, `nonlocal` (Day 11).
    
- Lambda functions for small inline tasks (Day 12).
    
- Built-in higher-order functions: `map`, `filter`, `zip`, `enumerate` (Day 13).
    
- Closures & decorators, combining behavior around functions (Day 14).  
    Use this day to reinforce by building integrated projects that exercise all these.
    

---

## 1) Mini Project Idea #1 — Calculator (with decorator logging)

**Requirements**

- Implement functions: `add`, `subtract`, `multiply`, `divide`.
    
- Support `*args` for e.g. `add(1,2,3,4)` returns 10.
    
- Use a decorator to log operation name, arguments, and result (to console or file).
    
- Demonstrate usage.
    

**Full sample**

```python
# calculator_with_logging.py
from functools import wraps
import datetime

def logger(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        start = datetime.datetime.now()
        result = func(*args, **kwargs)
        end = datetime.datetime.now()
        args_repr = ", ".join(map(str, args)) if args else ""
        kwargs_repr = ", ".join(f"{k}={v}" for k,v in kwargs.items())
        params = ", ".join(filter(None, [args_repr, kwargs_repr]))
        log_line = f"{start.isoformat()} | {func.__name__}({params}) -> {result} | duration: {end-start}"
        print(log_line)           # or write to file
        return result
    return wrapper

@logger
def add(*nums):
    return sum(nums)

@logger
def subtract(a, b):
    return a - b

@logger
def multiply(*nums):
    prod = 1
    for n in nums:
        prod *= n
    return prod

@logger
def divide(a, b):
    try:
        return a / b
    except ZeroDivisionError:
        return "Error: Division by zero"

if __name__ == "__main__":
    print(add(1,2,3))
    print(multiply(2,3,4))
    print(subtract(10, 3))
    print(divide(10, 2))
    print(divide(10, 0))
```

**What to test**

- `add()` with no args (should sum=0).
    
- `multiply()` with one arg.
    
- `divide()` with zero denominator (error handling).
    
- Observe logged lines (timestamp, function name, args, result).
    

**Extensions**

- Persist logs to a rotating log file using `logging` module.
    
- Add command-line interface to call operations.
    

---

## 2) Mini Project Idea #2 — Student Score Manager

**Requirements**

- Functions to add students with marks (use `*args` or list).
    
- Function to compute average, highest, lowest per student.
    
- Use `zip()` when you get two parallel lists (names, scores) to create dict.
    
- Rank students using `lambda` + `sorted()`.
    

**Full sample**

```python
# student_score_manager.py
from functools import reduce

class StudentManager:
    def __init__(self):
        self.students = {}  # {"Alice":[90,85,92], ...}

    def add_student(self, name, *marks):
        if not marks:
            raise ValueError("At least one mark required")
        self.students[name] = list(marks)

    def add_from_lists(self, names, marks_list):
        # marks_list is list of lists or list of tuples
        for name, marks in zip(names, marks_list):
            self.students[name] = list(marks)

    def average(self, name):
        marks = self.students.get(name, [])
        if not marks:
            return None
        return sum(marks) / len(marks)

    def stats(self, name):
        marks = self.students.get(name, [])
        if not marks:
            return {}
        return {
            "avg": sum(marks)/len(marks),
            "max": max(marks),
            "min": min(marks),
            "count": len(marks)
        }

    def rank_students(self):
        # returns list of tuples: [(name, avg), ...] sorted desc
        averages = ((name, self.average(name)) for name in self.students)
        ranked = sorted(averages, key=lambda x: (x[1] is not None, x[1]), reverse=True)
        return ranked

if __name__ == "__main__":
    sm = StudentManager()
    sm.add_student("Alice", 95, 85, 90)
    sm.add_student("Bob", 75, 80)
    sm.add_from_lists(["Charlie"], [[60, 70, 65]])
    print("Averages:")
    for name in sm.students:
        print(name, sm.average(name))
    print("Ranked:", sm.rank_students())
    print("Stats Alice:", sm.stats("Alice"))
```

**What to test**

- Add single student with `*marks`.
    
- Add many students using `add_from_lists` (uses `zip()`).
    
- Try ranking and ensure ordering is correct.
    
- Use `lambda` in `sorted()` as done.
    

**Extensions**

- Export ranks to CSV.
    
- Add validation for marks range (0–100).
    
- Add functionality to remove a student or update marks using `**kwargs` for metadata.
    

---

## Suggested evaluation / classroom activities for Day 15

- Pair-programming: one writes operations, the other writes decorator. Exchange code and review.
    
- Ask learners to add unit tests (simple `assert` lines) for `add`, `multiply`, `average`.
    
- Encourage refactoring: replace print-logging with `logging` module and set levels.
    

---

If you’d like, I can:

- Provide **ready-to-run notebooks** for each mini project.
    
- Add **test cases** / unit tests for both projects.
    
- Convert the ATM/Student/Calculator projects into incremental exercises so learners implement them step-by-step.
    