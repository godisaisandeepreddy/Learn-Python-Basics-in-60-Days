## 1️⃣ Running with Gunicorn / Uvicorn

FastAPI & Flask are development servers only — not for production.  
We use **Uvicorn** (ASGI) or **Gunicorn** (WSGI).

Run with Gunicorn + Uvicorn workers:

```bash
gunicorn -w 4 -k uvicorn.workers.UvicornWorker main:app
```

- `-w 4` → 4 workers (depends on CPU cores)
    
- `-k` → worker class (ASGI for FastAPI)
    

---

## 2️⃣ Environment Variables

Never hardcode secrets (like API keys, DB passwords).  
Use **`python-dotenv`**:

```bash
pip install python-dotenv
```

`.env` file:

```
SECRET_KEY=mysecret
DATABASE_URL=sqlite:///tasks.db
```

Load in code:

```python
from dotenv import load_dotenv
import os

load_dotenv()
SECRET_KEY = os.getenv("SECRET_KEY")
```

---

## 3️⃣ Logging & Monitoring

Use Python’s built-in `logging`:

```python
import logging

logging.basicConfig(
    level=logging.INFO,
    format="%(asctime)s [%(levelname)s] %(message)s"
)

logger = logging.getLogger(__name__)
logger.info("API started successfully!")
```

💡 In production, logs usually go to **files** or **log aggregation systems** (ELK stack, Loki, CloudWatch).

---

## 4️⃣ API Authentication Basics

- **API Keys** → simple token in headers.
    
- **JWT (JSON Web Tokens)** → stateless, widely used.
    

Example API Key check in FastAPI:

```python
from fastapi import Depends, HTTPException, Header

API_KEY = "mysecret"

def verify_api_key(x_api_key: str = Header(...)):
    if x_api_key != API_KEY:
        raise HTTPException(status_code=401, detail="Invalid API key")

@app.get("/secure-data", dependencies=[Depends(verify_api_key)])
def secure_data():
    return {"msg": "You have access!"}
```

---

## 5️⃣ Structuring Production Apps

Typical structure:

```
app/
    __init__.py
    main.py
    models/
        task.py
    routes/
        tasks.py
    services/
        auth.py
    config.py
```

- **models/** → database models
    
- **routes/** → API endpoints
    
- **services/** → business logic
    
- **config.py** → settings from `.env`
    

---

## 🏋️ Exercise

👉 Take your **Task Manager API** from Day 50 and:

1. Add logging (`logging` module).
    
2. Move configuration (DB URL, secret key) to `.env`.
    
3. Protect one endpoint with **API Key authentication**.
    
4. (Optional) Containerize with **Docker**:
    
    - Write a `Dockerfile`
        
    - Run `docker build -t task-api .`
        
    - Run `docker run -p 8000:8000 task-api`
        

---
