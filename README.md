# 🚀 Flask Todo App with Full CI/CD Pipeline (Docker + AWS EC2 + GitHub Actions)

A production-ready Todo web application built using Flask, containerized with Docker, deployed on AWS EC2, and automated using GitHub Actions CI/CD.

---

## 🌐 Live Demo
🔗 **[http://utkarsh-todo.duckdns.org](http://utkarsh-todo.duckdns.org)**  
*(Alternative Direct IP: [http://3.110.12.248](http://3.110.12.248))*

---

## 📸 Features Preview

### 🏠 Home Page
![Home](screenshot1.png)

### ➕ Add Todo
![Add](screenshot2.png)

---

## 🧱 Tech Stack

- **Backend**: Flask (Python)
- **Database**: SQLite / SQLAlchemy
- **Containerization**: Docker & Docker Hub
- **CI/CD**: GitHub Actions
- **Cloud Infrastructure**: AWS EC2 (Amazon Linux 2023)
- **Domain & DNS**: DuckDNS (`utkarsh-todo.duckdns.org`)

---

## ⚙️ Architecture

```
User → DuckDNS Domain → AWS EC2 (Port 80) → Docker Container → Flask App (Port 5000)
                                                    ↑
                                         GitHub Actions (CI/CD)
```

---

## 🚀 Features

- Add, update, and delete Todos seamlessly
- Fully dockerized Flask application
- Automated CI/CD pipeline triggered on every commit to `main`
- Zero manual deployment effort
- Live public deployment on AWS EC2

---

## 🔄 CI/CD Workflow

1. Code pushed to `main` branch on GitHub.
2. GitHub Actions builds the Docker image.
3. Image pushed to Docker Hub (`pandaverze/todo-flask-app`).
4. GitHub Actions SSHs into AWS EC2 instance.
5. EC2 pulls the latest Docker image.
6. Old container stopped and removed.
7. New container deployed automatically on Port 80 (`-p 80:5000`).

---

## 🐳 Running Locally with Docker

```bash
# Build the Docker image
docker build -t todo-flask-app .

# Run the container
docker run -p 5000:5000 todo-flask-app
```
Access locally in your browser at `http://localhost:5000`.