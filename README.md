# Docker Compose - Nginx Reverse Proxy with Multiple Services

A simple Docker Compose project demonstrating how to use **Nginx as a Reverse Proxy** to route requests to multiple backend services running in separate Docker containers.

## 📌 Project Overview

This project simulates a microservices architecture using Docker Compose.

The services are:

- Nginx (Reverse Proxy)
- Auth Service
- Order Service
- API Service
- Profile Service
- Delivery Service

Each backend service uses the lightweight `traefik/whoami` image to display container information, making it easy to verify that Nginx is routing requests correctly.

---

## 🏗️ Project Structure

```
.
├── docker-compose.yml
├── proxy
│   ├── nginx.conf
│   ├── default.conf
│   └── index.html
└── README.md
```

---

## 🛠️ Technologies

- Docker
- Docker Compose
- Nginx
- Traefik Whoami

---

## 🚀 Services

| Service | Image | Purpose |
|----------|-------|---------|
| proxy | nginx:latest | Reverse Proxy |
| auth | traefik/whoami | Authentication Service |
| order | traefik/whoami | Order Service |
| api | traefik/whoami | API Service |
| profile | traefik/whoami | Profile Service |
| delivery | traefik/whoami | Delivery Service |

---

## 🌐 Architecture

```
                 Client
                    │
                    ▼
          +-------------------+
          |      Nginx        |
          |   Reverse Proxy   |
          +-------------------+
          │   │   │   │   │
          │   │   │   │   │
          ▼   ▼   ▼   ▼   ▼
       Auth Order API Profile Delivery
```

---

## ▶️ Getting Started

Clone the repository:

```bash
git clone https://github.com/your-username/repository-name.git
cd repository-name
```

Start the containers:

```bash
docker compose up -d
```

Check running containers:

```bash
docker ps
```

Stop the project:

```bash
docker compose down
```

---

## 📂 Routing

Depending on your Nginx configuration, requests are forwarded to different services.

Example:

```
/
        -> Home Page

/auth
        -> Auth Service

/order
        -> Order Service

/api
        -> API Service

/profile
        -> Profile Service

/delivery
        -> Delivery Service
```

---

## 🎯 Learning Objectives

This project demonstrates:

- Docker Compose fundamentals
- Running multiple containers
- Docker networking
- Service discovery using container names
- Nginx Reverse Proxy configuration
- Volume mounting
- Port mapping

---

## 📸 Demo

You can add screenshots or GIFs here showing:

- Home page
- `/auth`
- `/order`
- `/api`
- `/profile`
- `/delivery`

---

## 📚 Future Improvements

- Replace `whoami` containers with real backend applications.
- Add Health Checks.
- Use environment variables.
- Add custom Docker networks.
- Add HTTPS with Let's Encrypt.
- Integrate Traefik.
- Deploy using Docker Swarm.

---

## 👨‍💻 Author

**Mahmoud Reda Saafan**

- GitHub: https://github.com/mahmoud-reda-00
- LinkedIn: https://www.linkedin.com/in/mahmoud-reda-saafan
