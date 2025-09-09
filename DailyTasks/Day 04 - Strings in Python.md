

---

## 1️⃣ What is a String?

- A **string** is a sequence of characters enclosed in quotes.
    
- Python allows **single (`'`), double (`"`), and triple quotes (`'''` or `"""`)**.
    

```python
s1 = 'Hello'
s2 = "World"
s3 = """This is
a multi-line
string"""
```

---

## 2️⃣ String Indexing & Slicing

### 🔹 Indexing (position of characters)

```python
word = "Python"

print(word[0])   # P (first character)
print(word[-1])  # n (last character)
print(word[2])   # t
```

### 🔹 Slicing (substrings)

```python
print(word[0:4])   # Pyth (index 0 to 3)
print(word[:3])    # Pyt
print(word[2:])    # thon
print(word[-3:])   # hon
print(word[::-1])  # nohtyP (reverse string)
```

---

## 3️⃣ String Concatenation & Repetition

```python
a = "Hello"
b = "World"

print(a + " " + b)   # Hello World
print(a * 3)         # HelloHelloHello
```

---

## 4️⃣ String Formatting

### 🔹 Old style (`%`)

```python
name = "Alice"
age = 25
print("My name is %s and I am %d years old." % (name, age))
```

### 🔹 `str.format()` method

```python
print("My name is {} and I am {} years old.".format("Bob", 30))
print("My name is {0} and I am {1}".format("Charlie", 28))
```

### 🔹 f-strings (Recommended) – Python 3.6+

```python
name = "Diana"
age = 22
print(f"My name is {name} and I am {age} years old.")
print(f"Next year, I will be {age + 1}.")
```

---

## 5️⃣ Useful String Methods

### 🔹 Changing case

```python
text = "python programming"
print(text.upper())    # PYTHON PROGRAMMING
print(text.lower())    # python programming
print(text.title())    # Python Programming
print(text.capitalize())  # Python programming
```

### 🔹 Checking strings

```python
print(text.startswith("py"))   # True
print(text.endswith("ing"))    # True
print(text.isalpha())          # False (contains space)
print("123".isdigit())         # True
```

### 🔹 Stripping spaces

```python
msg = "   hello   "
print(msg.strip())   # hello
print(msg.lstrip())  # remove left spaces
print(msg.rstrip())  # remove right spaces
```

### 🔹 Splitting & Joining

```python
data = "apple,banana,cherry"
fruits = data.split(",")  # ['apple', 'banana', 'cherry']

sentence = " ".join(fruits)
print(sentence)  # apple banana cherry
```

### 🔹 Find & Replace

```python
txt = "I love Java"
print(txt.replace("Java", "Python"))   # I love Python

print(txt.find("love"))   # 2 (index)
print(txt.find("C++"))    # -1 (not found)
```

---

## 6️⃣ String Immutability

- Strings **cannot be changed** in place.
    
- Example:
    

```python
s = "Hello"
# s[0] = "h" ❌ (Error)
s = "h" + s[1:]   # ✅ correct way
print(s)   # hello
```

---

## 7️⃣ Day 4 Exercises

1. Take a string input and print its **first and last character**.
    
2. Reverse a string using slicing.
    
3. Given a string `"Python is fun"`, extract:
    
    - `"Python"`
        
    - `"is"`
        
    - `"fun"`
        
4. Take a name and age as input, and print using all three formatting styles (`%`, `.format`, f-string`).
    
5. Convert `"learning python is interesting"` into:
    
    - Uppercase
        
    - Title case
        
    - Replace `"python"` with `"coding"`.
        
6. Split the string `"one,two,three,four"` into a list, and then join it with `"-"`.
    
7. Check if `"12345"` is numeric and `"Hello"` is alphabetic.
    
8. Remove spaces from `" Python Basics "`.
    

---

✅ By end of Day 4 → You’ll be able to handle **string slicing, formatting, f-strings, methods, and immutability**.

---
