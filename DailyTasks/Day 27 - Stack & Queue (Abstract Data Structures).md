
Python provides built-in ways to implement **stack and queue**, which are **abstract data structures** used for organizing data with specific rules.

---

## 1️⃣ Stack (LIFO – Last In, First Out)

- **Last element added** is **first to be removed**.
    
- Can be implemented using a **list** in Python.
    

### 🔹 Basic Operations

```python
# Stack using list
stack = []

# Push elements
stack.append(1)
stack.append(2)
stack.append(3)
print("Stack after pushes:", stack)  # [1, 2, 3]

# Pop elements (remove last)
top = stack.pop()
print("Popped:", top)                # 3
print("Stack now:", stack)           # [1, 2]

# Peek (top element without removing)
print("Top element:", stack[-1])     # 2
```

### 🔹 Applications of Stack

- Undo/Redo functionality in editors
    
- Function call stack
    
- Expression evaluation (infix to postfix conversion)
    

---

## 2️⃣ Queue (FIFO – First In, First Out)

- **First element added** is **first to be removed**.
    
- Implemented efficiently using **`collections.deque`**.
    

### 🔹 Basic Operations

```python
from collections import deque

# Initialize queue
q = deque([1, 2])

# Enqueue (add to rear)
q.append(3)
print("Queue after enqueue:", q)  # deque([1, 2, 3])

# Dequeue (remove from front)
first = q.popleft()
print("Dequeued:", first)         # 1
print("Queue now:", q)            # deque([2, 3])

# Peek front element
print("Front element:", q[0])     # 2
```

### 🔹 Applications of Queue

- Task scheduling (print queue, CPU scheduling)
    
- Breadth-First Search (BFS) in graphs
    
- Handling requests in web servers
    

---

## 3️⃣ Exercise: Browser History using Stack

```python
class BrowserHistory:
    def __init__(self):
        self.history = []
        self.forward_stack = []

    def visit(self, url):
        self.history.append(url)
        self.forward_stack.clear()  # visiting new page clears forward history
        print(f"Visited: {url}")

    def back(self):
        if len(self.history) > 1:
            self.forward_stack.append(self.history.pop())
            print(f"Back to: {self.history[-1]}")
        else:
            print("No previous page")

    def forward(self):
        if self.forward_stack:
            url = self.forward_stack.pop()
            self.history.append(url)
            print(f"Forward to: {url}")
        else:
            print("No forward page")

# Example usage
browser = BrowserHistory()
browser.visit("google.com")
browser.visit("github.com")
browser.visit("stackoverflow.com")
browser.back()     # Back to github.com
browser.back()     # Back to google.com
browser.forward()  # Forward to github.com
```

---

### 4️⃣ Key Takeaways

- **Stack** → LIFO, ideal for undo/redo, backtracking.
    
- **Queue** → FIFO, ideal for scheduling and BFS traversal.
    
- Python’s **list** and **`deque`** make implementation easy.
    
- Combining **stack & queue** allows building real-world applications like browser history or task schedulers.
    

---
