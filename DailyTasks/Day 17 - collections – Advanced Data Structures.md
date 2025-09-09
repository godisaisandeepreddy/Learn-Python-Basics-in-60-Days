

The `collections` module provides **specialized container datatypes** beyond Python’s built-in `list`, `dict`, `set`, and `tuple`.  
They are optimized for performance and specific use cases.

---

## 1️⃣ `Counter` – Counting Hashable Objects

- Helps count how many times each element appears.
    
- Works like a `dict` with elements as keys and counts as values.
    

```python
from collections import Counter

# Example 1: counting characters
c = Counter("banana")
print(c)  # Counter({'a': 3, 'n': 2, 'b': 1})

# Example 2: counting words
words = "apple orange apple banana apple orange"
c = Counter(words.split())
print(c)  # Counter({'apple': 3, 'orange': 2, 'banana': 1})

# Most common
print(c.most_common(2))  # [('apple', 3), ('orange', 2)]
```

---

## 2️⃣ `defaultdict` – Dictionary with Default Values

- Unlike normal dict, avoids `KeyError` by providing a default value.
    

```python
from collections import defaultdict

# Default value = 0
dd = defaultdict(int)
dd["a"] += 1
dd["b"] += 5
print(dd)  # defaultdict(<class 'int'>, {'a': 1, 'b': 5})

# Default value = list
dd_list = defaultdict(list)
dd_list["fruits"].append("apple")
dd_list["fruits"].append("banana")
print(dd_list)  # defaultdict(<class 'list'>, {'fruits': ['apple', 'banana']})
```

---

## 3️⃣ `deque` – Double-Ended Queue

- A fast list-like container with **O(1) append and pop from both ends**.
    

```python
from collections import deque

d = deque([1, 2, 3])
d.append(4)       # add right
d.appendleft(0)   # add left
print(d)          # deque([0, 1, 2, 3, 4])

d.pop()           # remove right
d.popleft()       # remove left
print(d)          # deque([1, 2, 3])
```

---

## 4️⃣ `namedtuple` – Tuples with Named Fields

- Creates tuple-like objects with named attributes.
    

```python
from collections import namedtuple

Point = namedtuple("Point", "x y")
p = Point(10, 20)

print(p)       # Point(x=10, y=20)
print(p.x)     # 10
print(p.y)     # 20

# Acts like both tuple and object
print(p[0], p[1])  # 10 20
```

---

## 5️⃣ `OrderedDict` – Ordered Dictionary

- A dictionary that preserves **insertion order**.
    
- Since Python 3.7+, normal dict also preserves order, but `OrderedDict` has **extra methods** (`move_to_end`, `popitem(last=True)` etc.).
    

```python
from collections import OrderedDict

od = OrderedDict()
od["a"] = 1
od["b"] = 2
od["c"] = 3

print(od)  # OrderedDict([('a', 1), ('b', 2), ('c', 3)])

od.move_to_end("a")  # move 'a' to end
print(od)  # OrderedDict([('b', 2), ('c', 3), ('a', 1)])
```

---

## 6️⃣ Exercise

👉 Use `Counter` to find the **top 3 most common words** in a sentence.

```python
from collections import Counter

sentence = "python is great and python is easy to learn and python is powerful"
words = sentence.split()

c = Counter(words)
print("Word counts:", c)
print("Top 3 words:", c.most_common(3))
```

✅ Output:

```
Word counts: Counter({'python': 3, 'is': 3, 'and': 2, 'great': 1, 'easy': 1, 'to': 1, 'learn': 1, 'powerful': 1})
Top 3 words: [('python', 3), ('is', 3), ('and', 2)]
```

---

By the end of **Day 17** → You’ll be comfortable with **special data structures** in `collections` that solve problems more efficiently than regular lists/dicts.

---
