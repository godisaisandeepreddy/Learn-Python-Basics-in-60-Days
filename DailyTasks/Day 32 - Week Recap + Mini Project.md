This day focuses on **reviewing all data structures, memory, and complexity concepts** learned in the past week and applying them in practical mini projects.

---

## 1️⃣ Recap of Key Concepts

### 🔹 Built-in Data Structures

|Structure|Mutable|Ordered|Use-case|
|---|---|---|---|
|List|Yes|Yes|Dynamic collection, sequence operations|
|Tuple|No|Yes|Fixed collection, faster access|
|Dict|Yes|Yes|Key-value mapping, fast lookup|
|Set|Yes|No|Unique items, fast membership|

### 🔹 Custom / Abstract Data Structures

- **Stack (LIFO)** → undo/redo, parsing
    
- **Queue (FIFO)** → scheduling, BFS
    
- **Linked List** → efficient insert/delete, dynamic data
    

### 🔹 Memory & Garbage Collection

- Python uses **heap + reference counting**
    
- **Circular references** handled by **`gc` module**
    
- `del` removes references but GC may be needed for cycles
    

### 🔹 Time Complexity

- O(1), O(log n), O(n), O(n log n), O(n²)
    
- Choose structures based on **lookup, insertion, deletion efficiency**
    

---

## 2️⃣ Mini Project Ideas

### 1️⃣ Text Analyzer

- **Goal:** Analyze word frequency and uniqueness in a text file.
    

```python
from collections import Counter

# Read text
with open("sample.txt") as f:
    text = f.read().lower().replace(".", "").replace(",", "")
words = text.split()

# Count frequency
freq = Counter(words)

# Unique words
unique_words = set(words)

# Display top 5 frequent words
print(freq.most_common(5))
print("Unique words:", len(unique_words))
```

**Complexity Insight:**

- List → O(n) lookup for counts
    
- Set → O(1) membership testing
    
- Counter uses optimized hashing
    

---

### 2️⃣ Task Manager

- **Goal:** Manage pending tasks (queue) and completed tasks (stack)
    

```python
from collections import deque

pending_tasks = deque(["task1", "task2", "task3"])
completed_tasks = []

# Process tasks
while pending_tasks:
    task = pending_tasks.popleft()  # O(1)
    print("Processing:", task)
    completed_tasks.append(task)    # O(1)

# Undo last task using stack
last_task = completed_tasks.pop()
print("Undo completed task:", last_task)
```

**Complexity Insight:**

- Queue (deque) → fast FIFO operations
    
- Stack (list) → fast LIFO operations
    

---

### 3️⃣ Linked List Playground

- **Goal:** Implement linked list operations
    

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_end(self, value):
        new_node = Node(value)
        if not self.head:
            self.head = new_node
            return
        curr = self.head
        while curr.next:
            curr = curr.next
        curr.next = new_node

    def traverse(self):
        curr = self.head
        while curr:
            print(curr.value, end=" -> ")
            curr = curr.next
        print("None")

# Example usage
ll = LinkedList()
for i in range(1, 6):
    ll.insert_end(i)
ll.traverse()
```

**Complexity Insight:**

- Linked list insert at end → O(n) (without tail pointer)
    
- List append → amortized O(1)
    

---

## 3️⃣ Key Takeaways

- Combining **data structures and complexity knowledge** is essential for **efficient solutions**.
    
- Mini projects help **practice real-world application** of built-in and custom structures.
    
- Always analyze **time and space trade-offs** for your solution.
    

---
