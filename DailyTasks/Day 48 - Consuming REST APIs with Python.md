Perfect 👍 Let’s begin Week 7 with **APIs and Data Handling**.

---

# 🗓️ Day 47: Consuming REST APIs with Python

## 🌍 What You’ll Learn

- Basics of **HTTP Methods** (`GET`, `POST`, `PUT`, `DELETE`)
    
- Using Python’s **`requests`** module
    
- Sending **query parameters** and **headers**
    
- Handling errors and responses
    

---

## 🔑 HTTP Basics

- **GET** → Retrieve data
    
- **POST** → Send new data
    
- **PUT** → Update existing data
    
- **DELETE** → Remove data
    

---

## 📌 Example: Basic GET Request

```python
import requests

# Example GET request
r = requests.get("https://jsonplaceholder.typicode.com/posts/1")

print("Status:", r.status_code)
print("Data:", r.json())   # JSON response
```

---

## 📌 Sending Query Params & Headers

```python
import requests

# Sending query parameters
r = requests.get("https://api.github.com/search/repositories",
                 params={"q": "python", "sort": "stars"})

print(r.json()["items"][0]["full_name"])  # Print top repo
```

```python
# Sending headers
headers = {"User-Agent": "MyApp"}
r = requests.get("https://api.github.com", headers=headers)

print(r.json())
```

---

## 📌 Handling Errors

```python
import requests

try:
    r = requests.get("https://jsonplaceholder.typicode.com/invalid-url")
    r.raise_for_status()  # Raise exception for HTTP errors
except requests.exceptions.HTTPError as e:
    print("HTTP Error:", e)
```

---

## 🏋️ Exercise

👉 Use the **OpenWeatherMap API** (or any free public API) to fetch and display current weather.

Example starter:

```python
import requests

API_KEY = "your_api_key"   # Get free from https://openweathermap.org/api
city = "London"

url = "https://api.openweathermap.org/data/2.5/weather"
params = {"q": city, "appid": API_KEY, "units": "metric"}

response = requests.get(url, params=params)
data = response.json()

print(f"Weather in {city}: {data['weather'][0]['description']}, Temp: {data['main']['temp']}°C")
```

---

👉 This will give you **real-time weather data**.
