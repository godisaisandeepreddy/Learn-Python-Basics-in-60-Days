This day is all about **tying together everything you’ve learned** in Week 6:

✅ Sorting Algorithms  
✅ Searching Algorithms  
✅ Heaps & Priority Queues  
✅ Iterators & Generators  
✅ Complexity & Performance Analysis

---

## 🔄 Recap Drills

1. **Sorting & Searching**
    

```python
nums = [5, 2, 9, 1, 7]
print("Sorted:", sorted(nums))  # Timsort O(n log n)

import bisect
pos = bisect.bisect_left(sorted(nums), 7)  # Binary search O(log n)
print("Found at index:", pos)
```

---

2. **Heaps & Priority Queues**
    

```python
import heapq

events = [(5, "Meeting"), (2, "Doctor"), (8, "Deadline")]
heapq.heapify(events)
print(heapq.heappop(events))  # (2, "Doctor")
```

---

3. **Generators & Lazy Evaluation**
    

```python
def read_large_file(path):
    with open(path) as f:
        for line in f:
            yield line.strip()

# process file line by line without loading into memory
for i, line in enumerate(read_large_file("data.txt")):
    if i < 5:
        print(line)
```

---

4. **Complexity Awareness**
    

- `list` lookup → O(n)
    
- `dict`/`set` lookup → O(1)
    
- Sorting → O(n log n)
    
- Heap operations → O(log n)
    

---

## 🎯 Mini Project Ideas

Pick **one** or try them all!

---

### 1. Event Scheduler (Heap + Dict)

```python
import heapq

class EventScheduler:
    def __init__(self):
        self.events = []   # min-heap
        self.lookup = {}   # fast dict lookup

    def add_event(self, time, name):
        heapq.heappush(self.events, (time, name))
        self.lookup[name] = time

    def next_event(self):
        return heapq.heappop(self.events)

# Example
scheduler = EventScheduler()
scheduler.add_event(5, "Meeting")
scheduler.add_event(2, "Doctor")
scheduler.add_event(8, "Deadline")

print("Next event:", scheduler.next_event())
```

---

### 2. Search Engine Toy (Binary Search vs Dict Lookup)

```python
import bisect, time

words = ["apple", "banana", "cherry", "date", "fig", "grape"]
words.sort()
word_dict = {w: True for w in words}

target = "cherry"

# Binary Search
start = time.time()
pos = bisect.bisect_left(words, target)
found = pos < len(words) and words[pos] == target
print("Binary Search:", found, "Time:", time.time()-start)

# Dict Lookup
start = time.time()
found = target in word_dict
print("Dict Lookup:", found, "Time:", time.time()-start)
```

---

### 3. Data Stream Processor (Generator + Rolling Average)

```python
def stream_numbers(n):
    for i in range(1, n+1):
        yield i

def rolling_average(stream, window_size=5):
    window = []
    for num in stream:
        window.append(num)
        if len(window) > window_size:
            window.pop(0)
        yield sum(window) / len(window)

# Example
for avg in rolling_average(stream_numbers(20), 5):
    print(avg)
```

---

## 🏋️ Exercise

👉 Choose **one mini project** and extend it:

- Add **complexity analysis** (timeit comparisons).
    
- Add **real-world simulation** (like reading from a CSV file for the Data Stream Processor).
    

---
