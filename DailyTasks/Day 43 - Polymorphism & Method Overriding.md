## 1️⃣ What is Polymorphism?

Polymorphism = **“many forms”** → same method name, but behavior depends on object.

Example:

```python
class Dog:
    def speak(self): print("Woof!")

class Cat:
    def speak(self): print("Meow!")

for animal in [Dog(), Cat()]:
    animal.speak()
```

---

## 2️⃣ Duck Typing in Python

In Python, if an object **behaves like a duck**, it’s treated like one → no need for strict type checks.

```python
class Bird:
    def fly(self): print("Bird flies")

class Airplane:
    def fly(self): print("Airplane flies")

for obj in [Bird(), Airplane()]:
    obj.fly()   # works for both!
```

---

## 3️⃣ Method Overriding

Child class **redefines parent method**.

```python
class Vehicle:
    def drive(self):
        print("Vehicle is moving")

class Car(Vehicle):
    def drive(self):   # overriding
        print("Car is driving fast")

Car().drive()   # Car is driving fast
```

---

## 4️⃣ Operator Overloading

Python allows customizing operators using **dunder methods**.

- `__add__` → `+`
    
- `__sub__` → `-`
    
- `__mul__` → `*`
    
- `__eq__` → `==`
    

Example:

```python
class Vector:
    def __init__(self, x, y):
        self.x, self.y = x, y
    
    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)
    
    def __sub__(self, other):
        return Vector(self.x - other.x, self.y - other.y)
    
    def __repr__(self):
        return f"Vector({self.x}, {self.y})"

v1 = Vector(2, 3)
v2 = Vector(4, 1)
print(v1 + v2)   # Vector(6, 4)
print(v1 - v2)   # Vector(-2, 2)
```

---

## 🏋️ Exercise

👉 Implement a **`Vector` class** with `+` and `-` operator overloading (done above).  
Extend it further with `*` (scalar multiplication) and `==` (equality check).

---
