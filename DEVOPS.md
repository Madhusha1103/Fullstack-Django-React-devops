# 🛠️ DevOps Documentation

This document describes the **DevOps practices, tools, and decisions** used in the *DevOps Assessment – Full-Stack Application* project.

---

## 🎯 Objective

The goal of this project is to demonstrate **core DevOps skills** by:

- Containerizing a full-stack application
- Orchestrating multiple services
- Ensuring environment consistency
- Enabling CI readiness using GitHub Actions

---

## 🐳 Containerization Strategy

### Backend (Django)
- Dockerized using a lightweight Python base image
- Dependencies installed via `requirements.txt`
- Application exposed on **port 8000**
- Uses Django’s development server for simplicity

### Frontend (React + Vite)
- Dockerized using a Node.js base image
- Vite dev server exposed on **port 5173**
- Communicates with backend via REST API

**Why Docker?**
- Ensures consistent runtime across environments
- Eliminates “works on my machine” issues
- Simplifies onboarding and deployment

---

## 📦 Docker Compose Orchestration

Docker Compose is used to manage **multiple containers** as a single application stack.

### Benefits:
- Single command to start/stop all services
- Automatic network creation
- Service-to-service communication
- Clear separation of frontend and backend

### Key Services:
- `backend` → Django API
- `frontend` → React UI

---

## 🔁 CI/CD – GitHub Actions

A GitHub Actions workflow is included to ensure **build reliability**.

### Workflow Capabilities:
- Triggers on every push
- Builds Docker images for both services
- Validates Dockerfiles
- Ensures no breaking changes are merged

### Workflow Location:
```text
.github/workflows/docker-build-push.yml
Note: The pipeline focuses on build validation, which is appropriate for assessment scope.

🔐 CORS & Networking
django-cors-headers is configured to allow frontend access

Backend accepts requests from frontend container and localhost

Docker Compose network enables seamless service communication

📸 Validation & Proof
The following were verified during execution:

Frontend UI accessible in browser

Backend API responding correctly

Docker containers running simultaneously

Docker Compose orchestration working

Django Admin page accessible

CI workflow present and valid

Screenshots were captured as proof of execution.

🧠 DevOps Best Practices Applied
Infrastructure as Code (Docker, Compose)

Separation of concerns (frontend vs backend)

Reproducible builds

Clean repository structure

CI readiness

Developer-friendly documentation

🚀 Future Improvements (Optional)
Production-ready builds (Nginx, Gunicorn)

Environment-based configuration

Cloud deployment (AWS / Azure / GCP)

Container registry push

Kubernetes orchestration

✅ Summary
This project demonstrates practical DevOps fundamentals using industry-standard tools.
It is suitable for development, CI validation, and future production enhancements.
