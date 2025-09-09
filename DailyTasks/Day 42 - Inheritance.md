Inheritance = **reusing existing class functionality in new classes**.  
It allows **code reuse**, **method overriding**, and **extending features**.

---

## 1️⃣ Single Inheritance

Child inherits from **one parent**.

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):  # Dog inherits from Animal
    def speak(self):  # Overriding parent method
        print("Woof!")

dog = Dog()
dog.speak()   # Woof!
```

---

## 2️⃣ Multiple Inheritance

Child inherits from **multiple parents**.

```python
class Flyer:
    def fly(self):
        print("I can fly")

class Swimmer:
    def swim(self):
        print("I can swim")

class Duck(Flyer, Swimmer):
    pass

d = Duck()
d.fly()    # I can fly
d.swim()   # I can swim
```

⚠️ **Note:** If same method exists in multiple parents → Python uses **MRO (Method Resolution Order)**.

---

## 3️⃣ Multilevel Inheritance

Inheritance in **chain**.

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def speak(self):
        print("Dog barks")

class Puppy(Dog):
    def speak(self):
        print("Puppy yaps")

p = Puppy()
p.speak()   # Puppy yaps
```

---

## 4️⃣ `super()` Keyword

Used to **call parent class constructor/method**.

```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        print(f"{self.name} makes a sound")

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)   # call parent constructor
        self.breed = breed

    def speak(self):
        super().speak()          # call parent method
        print(f"{self.name} barks!")

dog = Dog("Buddy", "Labrador")
dog.speak()
```

---

## 🏋️ Exercise

👉 Create a **Vehicle → Car → ElectricCar** hierarchy.

```python
class Vehicle:
    def __init__(self, brand):
        self.brand = brand
    
    def drive(self):
        print(f"{self.brand} is moving")

class Car(Vehicle):
    def drive(self):
        print(f"{self.brand} car is driving")

class ElectricCar(Car):
    def __init__(self, brand, battery_capacity):
        super().__init__(brand)
        self.battery_capacity = battery_capacity
    
    def drive(self):
        print(f"{self.brand} electric car with {self.battery_capacity}kWh battery is driving silently")

# Test
tesla = ElectricCar("Tesla", 75)
tesla.drive()
```

---
