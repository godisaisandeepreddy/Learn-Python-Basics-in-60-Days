
👉 This week you covered **Encapsulation, Inheritance, Polymorphism, Dunder Methods, Decorators, Context Managers, Abstract Classes**.  
Now let’s **apply all these concepts in a mini-project**.

---

## 🚀 Mini Project 1: **Library Management System**

```python
from abc import ABC, abstractmethod

class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author
        self.available = True

    def __str__(self):
        return f"{self.title} by {self.author} ({'Available' if self.available else 'Borrowed'})"


class Member(ABC):
    def __init__(self, name):
        self.name = name
        self.books = []

    @abstractmethod
    def borrow_limit(self):
        pass

    def borrow(self, book):
        if len(self.books) < self.borrow_limit() and book.available:
            self.books.append(book)
            book.available = False
            print(f"{self.name} borrowed {book.title}")
        else:
            print(f"{self.name} cannot borrow {book.title}")

    def return_book(self, book):
        if book in self.books:
            self.books.remove(book)
            book.available = True
            print(f"{self.name} returned {book.title}")


class RegularMember(Member):
    def borrow_limit(self):
        return 2


class PremiumMember(Member):
    def borrow_limit(self):
        return 5


class Library:
    def __init__(self):
        self.books = []

    def add_book(self, book):
        self.books.append(book)

    def show_books(self):
        for b in self.books:
            print(b)


# Demo
lib = Library()
lib.add_book(Book("1984", "George Orwell"))
lib.add_book(Book("Python Crash Course", "Eric Matthes"))

m1 = RegularMember("Alice")
m2 = PremiumMember("Bob")

lib.show_books()
m1.borrow(lib.books[0])
m2.borrow(lib.books[1])
lib.show_books()
```

✔ Uses **Encapsulation, Inheritance, Abstract Classes**.

---

## 🚀 Mini Project 2: **Banking System**

```python
class Account:
    def __init__(self, owner, balance=0):
        self._owner = owner
        self._balance = balance  # encapsulated

    def deposit(self, amount):
        self._balance += amount
        print(f"Deposited {amount}, New Balance: {self._balance}")

    def withdraw(self, amount):
        if amount <= self._balance:
            self._balance -= amount
            print(f"Withdrew {amount}, New Balance: {self._balance}")
        else:
            print("Insufficient funds")


class SavingsAccount(Account):
    def withdraw(self, amount):
        if amount > 1000:
            print("Withdrawal limit exceeded for Savings Account")
        else:
            super().withdraw(amount)


class CheckingAccount(Account):
    pass


# Demo
acc1 = SavingsAccount("Alice", 2000)
acc1.withdraw(1500)  # ❌ exceeds limit
acc1.withdraw(500)   # ✅ works
```

✔ Demonstrates **method overriding + encapsulation**.

---

## 🚀 Mini Project 3: **E-commerce Cart**

```python
class Product:
    def __init__(self, name, price):
        self.name = name
        self.price = price

    def __repr__(self):
        return f"{self.name} (${self.price})"


class Cart:
    def __init__(self):
        self.items = []

    def __len__(self):
        return len(self.items)

    def __getitem__(self, index):
        return self.items[index]

    def __add__(self, product):
        self.items.append(product)
        return self

    def total(self):
        return sum(p.price for p in self.items)


class Order:
    def __init__(self, cart):
        self.cart = cart

    def __enter__(self):
        print("Order started...")
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Order completed!")

    def checkout(self):
        print("Items:", self.cart.items)
        print("Total:", self.cart.total())


# Demo
cart = Cart()
cart + Product("Laptop", 1200) + Product("Mouse", 50)

with Order(cart) as order:
    order.checkout()
```

✔ Demonstrates **dunder methods + context manager**.

---

