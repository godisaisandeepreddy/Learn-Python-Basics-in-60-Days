A **linked list** is a **linear data structure** where elements are stored in **nodes**, and each node points to the next.  
Unlike lists, linked lists allow **efficient insertion and deletion** at any position.

---

## 1️⃣ Node Class

Each node contains:

- `data` → value of the node
    
- `next` → pointer to the next node
    

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

---

## 2️⃣ Singly Linked List

A linked list where each node points **only to the next node**.

### 🔹 Linked List Class

```python
class SinglyLinkedList:
    def __init__(self):
        self.head = None

    # Insert at beginning
    def insert_at_beginning(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    # Insert at end
    def insert_at_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        current = self.head
        while current.next:
            current = current.next
        current.next = new_node

    # Traverse and print
    def traverse(self):
        current = self.head
        while current:
            print(current.data, end=" -> ")
            current = current.next
        print("None")
```

### 🔹 Example Usage

```python
ll = SinglyLinkedList()
ll.insert_at_end(10)
ll.insert_at_beginning(5)
ll.insert_at_end(15)
ll.traverse()  # 5 -> 10 -> 15 -> None
```

---

## 3️⃣ Reverse a Linked List

### 🔹 Iterative Approach

```python
def reverse_linked_list(ll):
    prev = None
    current = ll.head
    while current:
        next_node = current.next
        current.next = prev
        prev = current
        current = next_node
    ll.head = prev

ll.traverse()            # 5 -> 10 -> 15 -> None
reverse_linked_list(ll)
ll.traverse()            # 15 -> 10 -> 5 -> None
```

### 🔹 Recursive Approach

```python
def reverse_recursive(node):
    if not node or not node.next:
        return node
    rest = reverse_recursive(node.next)
    node.next.next = node
    node.next = None
    return rest

ll.head = reverse_recursive(ll.head)
ll.traverse()  # 5 -> 10 -> 15 -> None
```

---

## 4️⃣ Optional: Doubly Linked List

- Each node has `prev` and `next` pointers.
    
- Allows **traversal in both directions**.
    

```python
class DoublyNode:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None
```

- Useful for **LRU caches, browser history, and undo-redo operations**.
    

---

### 5️⃣ Key Takeaways

- **Linked List** → efficient insertion/deletion compared to arrays.
    
- **Node class** is the building block.
    
- **Singly vs Doubly**: doubly adds backward traversal.
    
- **Reversing a linked list** can be done iteratively or recursively.
    

---

