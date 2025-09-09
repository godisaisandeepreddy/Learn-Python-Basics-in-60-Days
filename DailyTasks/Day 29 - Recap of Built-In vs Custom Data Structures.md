This day focuses on **reviewing all the data structures** covered so far, comparing **built-in vs custom implementations**, and practicing coding drills.

---

## 1️⃣ Built-In Data Structures

| Structure | Mutable | Ordered    | Access Time             | Notes                                    |
| --------- | ------- | ---------- | ----------------------- | ---------------------------------------- |
| List      | Yes     | Yes        | O(1) index, O(n) search | Dynamic array, flexible                  |
| Tuple     | No      | Yes        | O(1) index, O(n) search | Immutable, faster                        |
| Dict      | Yes     | Yes (3.7+) | O(1) lookup             | Key-value mapping                        |
| Set       | Yes     | No         | O(1) lookup             | Unique elements, mathematical operations |

---

## 2️⃣ Custom / Abstract Data Structures

|Structure|Implementation|Notes|
|---|---|---|
|Stack|list or custom class|LIFO, used for undo/redo, parsing|
|Queue|deque or custom class|FIFO, used for scheduling, BFS|
|Linked List|Node-based|Efficient insert/delete, used for dynamic data and complex structures|
|Doubly Linked List|Node with prev/next|Bidirectional traversal, useful for LRU cache|

---

## 3️⃣ Performance Considerations

- **Lists vs Linked Lists:**
    
    - Lists → fast random access, slow insert/delete in middle
        
    - Linked Lists → slow random access, fast insert/delete
        
- **Stacks & Queues:**
    
    - Use **list** for small stack/queue
        
    - Use **deque** for performance on large data
        
- **Dictionaries & Sets:**
    
    - Provide **constant-time lookup**
        
    - Use when uniqueness or key-value mapping is required
        

---

## 4️⃣ Mini Coding Drills

### 🔹 Drill 1: Reverse a String Using Stack

```python
def reverse_string(s):
    stack = list(s)
    reversed_str = ""
    while stack:
        reversed_str += stack.pop()
    return reversed_str

print(reverse_string("Python"))  # nohtyP
```

---

### 🔹 Drill 2: Check Balanced Parentheses Using Stack

```python
def is_balanced(expr):
    stack = []
    pairs = {")":"(", "}":"{", "]":"["}
    for ch in expr:
        if ch in "({[":
            stack.append(ch)
        elif ch in ")}]":
            if not stack or stack.pop() != pairs[ch]:
                return False
    return not stack

print(is_balanced("{[()]}"))  # True
print(is_balanced("{[(])}"))  # False
```

---

### 🔹 Drill 3: Implement Queue Using Two Stacks

```python
class QueueUsingStacks:
    def __init__(self):
        self.s1 = []
        self.s2 = []

    def enqueue(self, x):
        self.s1.append(x)

    def dequeue(self):
        if not self.s2:
            while self.s1:
                self.s2.append(self.s1.pop())
        if not self.s2:
            return None
        return self.s2.pop()

q = QueueUsingStacks()
q.enqueue(1)
q.enqueue(2)
q.enqueue(3)
print(q.dequeue())  # 1
print(q.dequeue())  # 2
```

---

## 5️⃣ Key Takeaways

- **Choose the right data structure** based on:
    
    - Mutability
        
    - Order requirement
        
    - Lookup/insert/delete performance
        
    - Use-case in real-world applications
        
- **Custom data structures** like stack, queue, linked list give **control over implementation details**.
    

---
