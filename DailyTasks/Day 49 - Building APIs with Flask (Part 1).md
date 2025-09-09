
## 🌍 What You’ll Learn

- Setting up Flask & creating your first API
    
- Defining routes with different HTTP methods
    
- Sending & receiving JSON data
    
- Handling path and query parameters
    

---

## 📌 Flask Setup & First App

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return {"message": "Hello API"}   # Flask auto converts dict → JSON

if __name__ == "__main__":
    app.run(debug=True)
```

👉 Run it with:

```bash
python app.py
```

and open [http://127.0.0.1:5000](http://127.0.0.1:5000/) in your browser.

---

## 📌 Routes with GET & POST

```python
from flask import request

# GET route
@app.route("/hello", methods=["GET"])
def hello():
    return {"message": "Hello, Flask!"}

# POST route
@app.route("/echo", methods=["POST"])
def echo():
    data = request.json   # JSON request body
    return {"you_sent": data}
```

---

## 📌 Path & Query Parameters

```python
# Path parameter
@app.route("/user/<int:user_id>")
def get_user(user_id):
    return {"user_id": user_id}

# Query parameter
# Example: /search?name=John
@app.route("/search")
def search():
    name = request.args.get("name")
    return {"query": name}
```

---

## 🏋️ Exercise

👉 Build a **Student Info API**:

- Create a route `/student/<int:id>`
    
- Return student details in JSON (name, age, grade).
    
- Use a dictionary as a fake database.
    

Example starter:

```python
students = {
    1: {"name": "Alice", "age": 20, "grade": "A"},
    2: {"name": "Bob", "age": 22, "grade": "B"},
    3: {"name": "Charlie", "age": 21, "grade": "A-"}
}

@app.route("/student/<int:student_id>")
def get_student(student_id):
    student = students.get(student_id)
    if student:
        return student
    return {"error": "Student not found"}, 404
```

---
