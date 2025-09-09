Encapsulation = **binding data + methods** together while **restricting direct access** to sensitive data.

---

## 1️⃣ Public, Protected, Private Variables

- **Public** → accessible everywhere
    
- **Protected (`_var`)** → convention (meant to be internal use, but still accessible)
    
- **Private (`__var`)** → name-mangled, cannot be accessed directly
    

```python
class Example:
    def __init__(self):
        self.public = "I am Public"
        self._protected = "I am Protected"
        self.__private = "I am Private"

obj = Example()

print(obj.public)       # ✅ Accessible
print(obj._protected)   # ⚠️ Accessible, but should be treated as internal
# print(obj.__private)  # ❌ AttributeError
print(obj._Example__private)  # ✅ Access via name mangling (not recommended)
```

---

## 2️⃣ Getter & Setter Methods

Encapsulation hides internal state → access/modification through **methods**.

```python
class BankAccount:
    def __init__(self, balance=0):
        self.__balance = balance  # private variable

    # Getter
    def get_balance(self):
        return self.__balance

    # Setter
    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
        else:
            print("Invalid deposit amount")

account = BankAccount(1000)
print(account.get_balance())  # 1000
account.deposit(500)
print(account.get_balance())  # 1500
```

---

## 3️⃣ Why Encapsulation is Important?

- **Data Security** → prevents unwanted modification
    
- **Controlled Access** → validate before updating
    
- **Code Maintainability** → hides complexity
    

Example: You wouldn’t want anyone to **directly modify bank balance** without checks.

---

## 🏋️ Exercise

👉 Implement a **Student** class with private `marks`, and provide getter & setter:

```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.__marks = marks  # private

    # Getter
    def get_marks(self):
        return self.__marks

    # Setter (with validation)
    def set_marks(self, new_marks):
        if 0 <= new_marks <= 100:
            self.__marks = new_marks
        else:
            print("Invalid marks, must be between 0 and 100")

s1 = Student("Alice", 85)
print(s1.get_marks())  # 85
s1.set_marks(95)
print(s1.get_marks())  # 95
s1.set_marks(150)      # Invalid marks
```

---
