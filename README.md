# 📝 Word Counter Application with Docker Compose

A hands-on multi-container application that demonstrates how to use Docker Compose in real-world style. The stack includes an input frontend, result frontend, job worker, Redis queue, and PostgreSQL database — all orchestrated with Docker Compose.

---

## 🎯 Overview

This application allows you to:
- Submit a block of text from the **Input Frontend**  
- A **Worker** picks up the job using a Redis queue  
- Word counts are computed and stored in PostgreSQL  
- The **Results Frontend** fetches and displays the results  

This setup shows how multiple services can **communicate**, **scale**, and **persist data**, using Docker Compose.

---

## 🧱 Project Architecture

```

Input Frontend --> Redis (job queue) --> Worker --> PostgreSQL (storage) --> Results Frontend

```

All services run on a custom Docker network, enabling seamless communication using service names.

### Components

| Service             | Role                                                  |
|----------------------|-------------------------------------------------------|
| Input Frontend       | Accepts user text and submits job to Redis           |
| Redis                | Message queue for jobs                                |
| Worker               | Picks jobs, counts words, stores results to DB        |
| PostgreSQL           | Persistent storage for word-count results             |
| Results Frontend     | Displays recent word-count results                    |

---

## 📁 Project Structure

```

/
├── docker-compose.yml
├── input-frontend/
│   ├── Dockerfile
│   ├── app.py
│   └── templates/index.html
├── results-frontend/
│   ├── Dockerfile
│   ├── app.py
│   └── templates/results.html
├── worker/
│   ├── Dockerfile
│   └── worker.py
├── db/
│   └── init.sql
└── README.md  ← (you’re here)

````

---

## 🚀 Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/shyamdevk/Word-Counter-Application-with-Docker-Compose.git
````

2. **Start all services (build if needed)**

   ```bash
   docker compose up --build
   ```

   Or to run in the background:

   ```bash
   docker compose up -d --build
   ```

3. **Access the frontends**

   * Input Frontend → `http://localhost:5000`
   * Results Frontend → `http://localhost:5001`
## 📸 Application Screenshots

### 📝 Input Screen
![Input Screen](./images/inp.png)

### 📊 Output Screen
![Output Screen](./images/out.png)


4. **Submit text** → View word-count results.

5. **Stop and clean up**

   ```bash
   docker compose down
   ```

   To remove volumes too:

   ```bash
   docker compose down -v
   ```

---

## 🛠 Why This Project Matters

* Demonstrates how to orchestrate a full stack of services using Docker Compose
* Shows usage of a message-queue (Redis) + background worker pattern
* Illustrates persistent data storage with PostgreSQL
* Highlights inter-service networking, portability, and reproducibility with Docker

---

## 📚 What You’ll Learn

* How to define services, networks, volumes in `docker-compose.yml`
* How services communicate by name in a custom Docker network
* How to build multi-service applications with Docker Compose
* How to persist data outside containers (so it's safe after restarts)
* Basic microservice architecture concepts

---

## 📌 Tips & Notes

* Make sure Docker is installed on your machine
* Use `docker compose ps` to see running services
* Use `docker compose logs <service>` for service-specific logs
* If you make changes in code, re-run with `--build` to rebuild images
* Develop locally by editing `input-frontend` or `worker`, then rebuild

---

## 🔗 Links & Resources

* [Docker Compose Documentation](https://docs.docker.com/compose/)
* [Redis Official Image](https://hub.docker.com/_/redis)
* [PostgreSQL Official Image](https://hub.docker.com/_/postgres)

---

## ✅ Conclusion

This Word Counter stack is an excellent **learning project** for anyone wanting to get hands-on with Docker Compose, multi-container applications, and service orchestration.
Clone, explore, tweak, and learn how containers can work together — and how Docker Compose simplifies it all.

---




::contentReference[oaicite:2]{index=2}
```
