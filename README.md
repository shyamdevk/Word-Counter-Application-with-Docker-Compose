# 📝 Word Counter Application using Docker Compose

A simple and complete **multi-container application** built using **Docker Compose**.  
It takes user input text, processes the job using a worker queue, stores results in PostgreSQL, and displays output through a results frontend.

---

## 📸 Application Screenshots

### 📝 Input Screen
![Screenshot](https://github.com/shyamdevk/Word-Counter-Application-with-Docker-Compose/blob/images/archi.png)

### 📊 Output Screen
![Output Screen](./images/out.png)

---

## 🚀 Project Overview

This application demonstrates how multiple independent components can work together using **Docker Compose**.  
The system flow is:

```

Input Frontend → Redis Queue → Worker → PostgreSQL DB → Output Frontend

```

Each part runs in its own container and communicates through a private Docker network.

---

## 🧱 Architecture Summary

| Component | Description |
|----------|-------------|
| **Input Frontend** | Accepts text and sends job to Redis |
| **Redis Queue** | Handles background job message queue |
| **Worker** | Processes text and stores results in database |
| **PostgreSQL DB** | Stores persistent results |
| **Results Frontend** | Displays processed word counts |

---

## 🛠 Technologies Used (With Percentage Contribution)

| Technology | Usage (%) | Role |
|-----------|-----------|------|
| **Python (Flask)** | 40% | Powers the input & output frontend |
| **Docker & Docker Compose** | 30% | Container orchestration & multi-service setup |
| **Redis** | 10% | Job queue for background processing |
| **PostgreSQL** | 15% | Database for storing word count results |
| **Worker Service (Python)** | 5% | Processes jobs asynchronously |

---

## 📁 Project Structure

```

/
├── docker-compose.yml
├── input-frontend/
│   ├── app.py
│   ├── Dockerfile
│   └── templates/index.html
├── results-frontend/
│   ├── app.py
│   ├── Dockerfile
│   └── templates/results.html
├── worker/
│   ├── worker.py
│   └── Dockerfile
├── db/
│   └── init.sql
└── images/
├── inp.png
└── out.png

````

---

## 🚀 How to Run the Project

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/shyamdevk/Word-Counter-Application-with-Docker-Compose.git
cd Word-Counter-Application-with-Docker-Compose
````

### 2️⃣ Start Services

```bash
docker compose up --build
```

Run in background:

```bash
docker compose up -d --build
```

### 3️⃣ Access the App

| Service              | URL                                            |
| -------------------- | ---------------------------------------------- |
| **Input Frontend**   | [http://localhost:5000](http://localhost:5000) |
| **Results Frontend** | [http://localhost:5001](http://localhost:5001) |

### 4️⃣ Stop Everything

```bash
docker compose down
```

Remove volumes too:

```bash
docker compose down -v
```

---

## 💡 What You Learn From This Project

* How Docker Compose links multiple services
* Using Redis as a job queue
* Background processing with a worker service
* Persisting data with PostgreSQL
* Structuring containerized applications cleanly
* Building real multi-container microservice-like architecture

---

## 👍 Final Notes

This project is perfect for **beginners learning Docker Compose**, multi-container apps, and real-world orchestration patterns.
You can extend it by adding API, authentication, or scaling services.

---

