
## 📌 1. FastAPI Setup

Install dependencies:

```bash
pip install fastapi uvicorn
```

Run the server:

```bash
uvicorn main:app --reload
```

Basic app:

```python
# main.py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def home():
    return {"msg": "Hello FastAPI"}
```

---

## 📌 2. Automatic Docs

- Swagger UI: 👉 `http://127.0.0.1:8000/docs`
    
- ReDoc: 👉 `http://127.0.0.1:8000/redoc`
    

FastAPI generates docs automatically from code + type hints ✅.

---

## 📌 3. Request Body Validation with Pydantic

```python
from pydantic import BaseModel

class Task(BaseModel):
    title: str
    description: str = None
    done: bool = False
```

---

## 📌 4. Async Endpoints

```python
@app.get("/items")
async def get_items():
    return {"items": ["apple", "banana", "mango"]}
```

---

## 📌 5. Full CRUD Example – Task Manager

```python
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel

app = FastAPI()

# Pydantic model
class Task(BaseModel):
    title: str
    description: str = None
    done: bool = False

# In-memory DB
tasks = {}

@app.post("/tasks")
def create_task(task: Task):
    task_id = len(tasks) + 1
    tasks[task_id] = task
    return {"id": task_id, **task.dict()}

@app.get("/tasks/{task_id}")
def get_task(task_id: int):
    task = tasks.get(task_id)
    if not task:
        raise HTTPException(status_code=404, detail="Task not found")
    return {"id": task_id, **task.dict()}

@app.put("/tasks/{task_id}")
def update_task(task_id: int, task: Task):
    if task_id not in tasks:
        raise HTTPException(status_code=404, detail="Task not found")
    tasks[task_id] = task
    return {"id": task_id, **task.dict()}

@app.delete("/tasks/{task_id}")
def delete_task(task_id: int):
    if task_id not in tasks:
        raise HTTPException(status_code=404, detail="Task not found")
    del tasks[task_id]
    return {"msg": f"Task {task_id} deleted"}
```

---

## 🏋️ Exercise

👉 Build a **Task Manager API** using FastAPI:

1. **POST** → Create task
    
2. **GET** → Retrieve single/all tasks
    
3. **PUT** → Update task
    
4. **DELETE** → Delete task
    
5. Test via **Swagger UI (`/docs`)**
    

---
