
## 📌 1. Structuring a Flask App

Instead of putting everything in one file, we use **blueprints** for modularity.

```python
# app/__init__.py
from flask import Flask
from .student_routes import student_bp

def create_app():
    app = Flask(__name__)
    app.register_blueprint(student_bp, url_prefix="/students")
    return app
```

```python
# app/student_routes.py
from flask import Blueprint, request, jsonify

student_bp = Blueprint("students", __name__)

students = {
    1: {"name": "Alice", "age": 20, "grade": "A"},
    2: {"name": "Bob", "age": 22, "grade": "B"}
}

@student_bp.route("/<int:student_id>", methods=["GET"])
def get_student(student_id):
    student = students.get(student_id)
    if student:
        return jsonify(student)
    return jsonify(error="Student not found"), 404
```

```python
# run.py
from app import create_app

app = create_app()

if __name__ == "__main__":
    app.run(debug=True)
```

---

## 📌 2. Request Validation

Before using incoming data, **validate** it.

```python
@student_bp.route("/", methods=["POST"])
def add_student():
    data = request.get_json()
    if not data or "name" not in data or "age" not in data:
        return jsonify(error="Invalid input"), 400
    new_id = max(students.keys()) + 1
    students[new_id] = data
    return jsonify({"id": new_id, **data}), 201
```

---

## 📌 3. Error Handling & HTTP Status Codes

```python
from flask import jsonify

@student_bp.errorhandler(404)
def not_found(e):
    return jsonify(error="Resource not found"), 404

@student_bp.errorhandler(500)
def server_error(e):
    return jsonify(error="Internal Server Error"), 500
```

---

## 📌 4. Middleware Basics

Middleware runs **before/after each request**.

```python
@student_bp.before_request
def before_req():
    print("Incoming request...")

@student_bp.after_request
def after_req(response):
    print("Outgoing response...")
    return response
```

---

## 📌 5. API Testing Tools

- **Postman** → GUI tool for testing APIs.
    
- **Insomnia** → Alternative to Postman.
    
- **cURL** → Command-line tool (`curl -X GET http://127.0.0.1:5000/students/1`).
    

---

## 🏋️ Exercise

👉 Extend your **Student API**:

1. Add **POST** with validation (name, age required).
    
2. Add **PUT** to update student details.
    
3. Add **DELETE** with proper status codes.
    
4. Add **error handling** for invalid student IDs.
    

---

