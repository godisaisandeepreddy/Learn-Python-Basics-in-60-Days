Object-Oriented Programming (OOP) is one of the most powerful paradigms in Python.

---

## 1️⃣ What is OOP? Why use it?

- **OOP (Object-Oriented Programming)** is a way to structure code using **objects** (real-world entities).
    
- Each object has:
    
    - **Attributes (data/state)** → variables inside the object
        
    - **Methods (behavior)** → functions that belong to the object
        

✅ Benefits:

- Makes code **reusable** and **organized**
    
- Encapsulation (grouping data + behavior together)
    
- Easier to model **real-world entities**
    

---

## 2️⃣ Defining a Class & Creating Objects

```python
class Car:
    def __init__(self, brand, model):   # Constructor
        self.brand = brand              # Instance variable
        self.model = model

    def drive(self):                    # Method
        print(f"{self.brand} {self.model} is driving")

# Create objects (instances)
car1 = Car("Tesla", "Model 3")
car2 = Car("BMW", "X5")

# Call method
car1.drive()   # Tesla Model 3 is driving
car2.drive()   # BMW X5 is driving
```

---

## 3️⃣ Instance Variables vs Class Variables

- **Instance Variables**: unique to each object
    
- **Class Variables**: shared across all objects
    

```python
class Dog:
    species = "Canine"   # Class variable (same for all dogs)

    def __init__(self, name):
        self.name = name   # Instance variable (unique per dog)

dog1 = Dog("Buddy")
dog2 = Dog("Charlie")

print(dog1.name, dog1.species)  # Buddy Canine
print(dog2.name, dog2.species)  # Charlie Canine

# Change instance variable
dog1.name = "Max"
print(dog1.name, dog2.name)  # Max Charlie

# Change class variable
Dog.species = "Doggo"
print(dog1.species, dog2.species)  # Doggo Doggo
```

---

## 4️⃣ The `__init__` Method (Constructor)

- Called automatically when creating an object
    
- Initializes object state (sets up attributes)
    

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        print(f"My name is {self.name} and I am {self.age} years old.")

s1 = Student("Alice", 21)
s1.introduce()   # My name is Alice and I am 21 years old.
```

---

## 🏋️ Exercise

👉 Create a **Book** class:

```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

    def get_info(self):
        return f"'{self.title}' by {self.author}"

# Example
b1 = Book("1984", "George Orwell")
b2 = Book("The Alchemist", "Paulo Coelho")

print(b1.get_info())  # '1984' by George Orwell
print(b2.get_info())  # 'The Alchemist' by Paulo Coelho
```

---
