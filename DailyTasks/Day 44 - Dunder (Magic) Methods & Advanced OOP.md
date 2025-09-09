
## 1️⃣ What are Dunder Methods?

- "Dunder" = **Double UNDerscore** (like `__init__`, `__len__`)
    
- They let you define how your class behaves with **Python built-ins, operators, and functions**.
    
- Example: `len(obj)` → Python internally calls `obj.__len__()`
    

---

## 2️⃣ Common Dunder Methods

### 📝 String Representations

- `__str__`: User-friendly string
    
- `__repr__`: Unambiguous, for developers/debugging
    

```python
class Book:
    def __init__(self, title, author):
        self.title, self.author = title, author
    
    def __str__(self):
        return f"{self.title} by {self.author}"   # user
    
    def __repr__(self):
        return f"Book('{self.title}', '{self.author}')"   # dev

b = Book("1984", "Orwell")
print(str(b))   # 1984 by Orwell
print(repr(b))  # Book('1984', 'Orwell')
```

---

### 🔢 Length & Comparisons

```python
class Team:
    def __init__(self, members):
        self.members = members
    
    def __len__(self):
        return len(self.members)
    
    def __eq__(self, other):
        return len(self) == len(other)
    
    def __lt__(self, other):  # less than
        return len(self) < len(other)

a = Team(["A", "B"])
b = Team(["X", "Y", "Z"])
print(len(a))       # 2
print(a == b)       # False
print(a < b)        # True
```

---

### 📦 Item Access (`__getitem__`, `__setitem__`)

```python
class MyList:
    def __init__(self, data):
        self.data = data
    
    def __getitem__(self, idx):
        return self.data[idx]
    
    def __setitem__(self, idx, value):
        self.data[idx] = value

nums = MyList([10, 20, 30])
print(nums[1])    # 20
nums[1] = 99
print(nums[1])    # 99
```

---

## 3️⃣ Behind the Scenes

- `len(obj)` → `obj.__len__()`
    
- `obj1 == obj2` → `obj1.__eq__(obj2)`
    
- `obj[i]` → `obj.__getitem__(i)`
    
- `print(obj)` → `obj.__str__()`
    

---

## 🏋️ Exercise

👉 Build a **`ShoppingCart` class** that behaves like a list:

- Add items with `append()`
    
- Access items with `cart[i]`
    
- Get length with `len(cart)`
    
- Pretty print with `__str__`
    

```python
class ShoppingCart:
    def __init__(self):
        self.items = []
    
    def __len__(self):
        return len(self.items)
    
    def __getitem__(self, idx):
        return self.items[idx]
    
    def __setitem__(self, idx, value):
        self.items[idx] = value
    
    def __str__(self):
        return f"Cart: {', '.join(self.items)}"
    
    def append(self, item):
        self.items.append(item)

cart = ShoppingCart()
cart.append("Apple")
cart.append("Banana")
print(cart)           # Cart: Apple, Banana
print(len(cart))      # 2
print(cart[0])        # Apple
```

---
