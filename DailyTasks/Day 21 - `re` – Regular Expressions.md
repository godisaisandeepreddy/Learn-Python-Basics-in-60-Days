
The `re` module allows **pattern matching and text manipulation** using **regular expressions (regex)**. It is extremely useful for **validation, searching, and text parsing**.

---

## 1️⃣ Basics of Regular Expressions

- Regular expressions are **patterns** used to match strings.
    
- Python uses the `re` module:
    

```python
import re
```

### 🔹 Common Symbols

|Symbol|Meaning|
|---|---|
|`.`|Any character except newline|
|`^`|Start of string|
|`$`|End of string|
|`*`|0 or more repetitions|
|`+`|1 or more repetitions|
|`?`|0 or 1 repetition|
|`{n}`|Exactly n repetitions|
|`{n,m}`|Between n and m repetitions|
|`[]`|Character set|
|`|`|
|`\d`|Digit `[0-9]`|
|`\D`|Non-digit|
|`\s`|Whitespace|
|`\S`|Non-whitespace|
|`\w`|Word character `[a-zA-Z0-9_]`|
|`\W`|Non-word character|

---

## 2️⃣ Common `re` Functions

### 🔹 `re.match()`

- Checks **if the pattern matches at the beginning** of the string.
    

```python
import re

text = "Hello123"
pattern = r"Hello"

match = re.match(pattern, text)
if match:
    print("Matched:", match.group())
```

### 🔹 `re.search()`

- Searches **anywhere in the string**.
    

```python
match = re.search(r"\d+", text)  # find first digit sequence
print(match.group())  # 123
```

### 🔹 `re.findall()`

- Returns **all matches** as a list.
    

```python
text = "I have 2 cats and 3 dogs."
numbers = re.findall(r"\d+", text)
print(numbers)  # ['2', '3']
```

### 🔹 `re.split()`

- Split string by a pattern.
    

```python
text = "apple,banana;orange|mango"
fruits = re.split(r"[,;|]", text)
print(fruits)  # ['apple', 'banana', 'orange', 'mango']
```

### 🔹 `re.sub()`

- Replace **pattern matches** with a string.
    

```python
text = "I have 2 cats and 3 dogs."
new_text = re.sub(r"\d+", "X", text)
print(new_text)  # I have X cats and X dogs.
```

---

## 3️⃣ Grouping and Capturing

- Use parentheses `( )` to capture groups.
    

```python
text = "My email is test@example.com"
pattern = r"(\w+)@(\w+)\.(\w+)"
match = re.search(pattern, text)
if match:
    print(match.groups())  # ('test', 'example', 'com')
```

---

## 4️⃣ Flags

- `re.IGNORECASE` or `re.I` → case-insensitive
    
- `re.MULTILINE` or `re.M` → `^` and `$` match each line
    
- `re.DOTALL` or `re.S` → `.` matches newline
    

```python
text = "Hello\nhello"
matches = re.findall(r"hello", text, re.I)
print(matches)  # ['Hello', 'hello']
```

---

## 5️⃣ Exercises

1. Extract all numbers from the text: `"The price is 300 and discount is 50"`.
    
2. Validate email addresses: `"test@example.com"`, `"abc@xyz"`, `"name@domain.co"`.
    
3. Replace all whitespace in a string with underscores.
    
4. Extract all words starting with capital letters from `"Hello World from Python"`.
    
5. Extract **area code** from phone numbers like `(123)-456-7890`.
    

---

✅ By the end of **Day 21** → You’ll be able to **search, extract, replace, and validate text patterns efficiently** using `re`.

---
