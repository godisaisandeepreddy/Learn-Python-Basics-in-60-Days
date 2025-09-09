Heaps are **binary trees** optimized for quick access to the smallest (or largest) element. In Python, heaps are implemented using **lists** in the `heapq` module.

---

## 1️⃣ Min Heap (default in Python)

```python
import heapq

nums = [5, 1, 8, 2]
heapq.heapify(nums)   # convert list into a heap
print(nums)           # internally arranged as heap

print(heapq.heappop(nums))  # 1 (smallest element)
print(heapq.heappop(nums))  # 2
```

🔹 Always pops the **smallest** element first.

---

## 2️⃣ Max Heap (using value inversion)

Python doesn’t have a built-in max heap, but you can simulate it by storing **negative values**.

```python
import heapq

nums = [5, 1, 8, 2]
max_heap = [-n for n in nums]
heapq.heapify(max_heap)

print(-heapq.heappop(max_heap))  # 8 (largest)
print(-heapq.heappop(max_heap))  # 5
```

---

## 3️⃣ Use Cases of Heaps

- **Dijkstra’s shortest path algorithm**
    
- **Task scheduling** (next earliest task first)
    
- **Finding top-k largest/smallest elements**
    

---

## 4️⃣ Priority Queue (`queue.PriorityQueue`)

If you need **thread-safe priority queues**, use this class.

```python
from queue import PriorityQueue

pq = PriorityQueue()
pq.put((2, "task low priority"))
pq.put((1, "task high priority"))
pq.put((3, "task very low priority"))

while not pq.empty():
    print(pq.get())
```

Output (smallest priority first):

```
(1, 'task high priority')
(2, 'task low priority')
(3, 'task very low priority')
```

---

## 5️⃣ Exercise

👉 **Find the top 3 largest elements from a list using `heapq`.**

```python
import heapq

nums = [5, 1, 8, 2, 10, 7, 6]
top3 = heapq.nlargest(3, nums)
print("Top 3 largest:", top3)   # [10, 8, 7]
```

Similarly, you can use:

```python
smallest3 = heapq.nsmallest(3, nums)
print("Top 3 smallest:", smallest3)   # [1, 2, 5]
```

---
