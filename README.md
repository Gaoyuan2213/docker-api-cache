# 🚀 Cloud-Ready Dockerized Cache API (with Frontend)

A production-style key-value cache service built with **FastAPI + Redis + Docker**, deployed on **AWS EC2**, and featuring a simple **Web Frontend UI**.

This project simulates a real-world cache service like Redis Cloud / Upstash, providing both an API and a browser interface.

---

## 🌟 Features

✅ RESTful Cache API  
✅ API Key Authentication  
✅ Dockerized Microservices  
✅ Redis for high-speed storage  
✅ TTL Support (Auto expiry)  
✅ AWS Cloud Deployment  
✅ Docker Compose Networking  
✅ Web Frontend Dashboard  
✅ Real-world architecture design  

---

## 🏗️ System Architecture

```
┌──────────────────────┐
│     Browser / UI     │
│     Frontend App     │
└───────────┬──────────┘
            │  HTTP
            ▼
┌──────────────────────┐
│   FastAPI Container  │
│   Port: 8000         │
│   API Server         │
└───────────┬──────────┘
            │ Docker Network
            ▼
┌──────────────────────┐
│   Redis Container    │
│   Port: 6379         │
│   In-Memory Cache    │
└──────────────────────┘
```

---
## Two commands configure
docker-compose down
docker-compose up --build -d
## 🔐 API Authentication

All API requests require an API Key:

**Header format:**
```
X-API-Key: my-secret-key-123
```

Requests without valid key will return:

```json
{ "detail": "Invalid API Key" }
```

---

## 🌐 Live Deployment

Public AWS Server:

```
http://3.99.213.39:8000
```

---

## 🖥️ Frontend Web Panel

You have a frontend UI for interacting with the system.

Access it in your browser:
```
http://3.99.213.39
```

Frontend supports:
- Adding cache key/value
- Setting TTL
- Viewing all keys
- Deleting keys

---

## 📦 API Endpoints

### 1. Store Data
**POST** `/cache`

```bash
curl -X POST http://3.99.213.39:8000/cache ^
  -H "Content-Type: application/json" ^
  -H "X-API-Key: my-secret-key-123" ^
  -d "{\"key\":\"city\",\"value\":\"Halifax\",\"ttl\":60}"
```

---

### 2. Get Data
**GET** `/cache/{key}`

```bash
curl http://3.99.213.39:8000/cache/city ^
  -H "X-API-Key: my-secret-key-123"
```

---

### 3. Delete Data
**DELETE** `/cache/{key}`

```bash
curl -X DELETE http://3.99.213.39:8000/cache/city ^
  -H "X-API-Key: my-secret-key-123"
```

---

### 4. List All Keys
**GET** `/cache`

```bash
curl http://3.99.213.39:8000/cache ^
  -H "X-API-Key: my-secret-key-123"
```

---

## 🐳 Local Docker Setup

Make sure Docker & Docker Compose are installed.

```bash
docker-compose up --build -d
```

View containers:

```bash
docker ps
```

---

## 📁 Project Structure

```
docker-api-cache/
│
├── app.py                 # FastAPI backend
├── frontend/              # Frontend UI
├── Dockerfile
├── docker-compose.yml
├── pyproject.toml
└── README.md
```

---

## ☁️ AWS Deployment Steps (Summary)

1. SSH to server  
2. Clone project  
3. Run:

```bash
docker-compose up --build -d
```

4. Access:
- API: `http://3.99.213.39:8000`
- Frontend: `http://3.99.213.39`

---

## 🎯 Use Cases

| Scenario | Use |
|------|------|
| Temporary session storage | Login sessions |
| Microservices cache | Speed up APIs |
| Frontend state | Cache user temp data |
| Database proxy | Reduce DB load |
| Demo cloud platform | Learning, portfolio |

---

## 👨‍💻 Author

**Gaoyuan Zhang**  
Project: Cloud-Ready Dockerized Cache API  
Deployed: AWS EC2  
Skills: Docker • FastAPI • Redis • Cloud • Networking • API Design

---

## 🚀 Future Upgrades

✔ Multi-User System  
✔ Rate Limiter  
✔ Web-based Monitoring  
✔ HTTPS + Domain  
✔ Dashboard Key Manager  

---
