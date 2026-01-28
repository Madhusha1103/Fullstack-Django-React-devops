
# 🚀 DevOps Assessment – Full-Stack Application

A simple **Hello World full-stack application** built with **Django (Backend)** and **React + Vite (Frontend)**, fully containerized using **Docker** and orchestrated with **Docker Compose**.

This project demonstrates core **DevOps fundamentals** including containerization, multi-service orchestration, environment consistency, and CI readiness.

---

## 📌 Project Overview

### 🔧 Tech Stack

**Backend**
- Django (REST API)
- Python 3.11
- django-cors-headers

**Frontend**
- React (Vite)
- TypeScript
- Axios
- Responsive UI

**DevOps**
- Docker
- Docker Compose
- GitHub Actions (CI – Docker build validation)

---

## 🧱 Project Structure

```text
devops-assessment/
├── backend/                 # Django backend
│   ├── Dockerfile
│   ├── requirements.txt
│   └── manage.py
├── frontend/                # React frontend
│   ├── Dockerfile
│   ├── package.json
│   └── vite.config.ts
├── docker-compose.yml       # Multi-container orchestration
├── .github/workflows/       # CI pipeline
│   └── docker-build-push.yml
└── README.md

🏗️ Architecture
┌──────────────┐        HTTP        ┌──────────────┐
│  Frontend    │  ───────────────▶ │   Backend    │
│  React/Vite  │                   │   Django API │
│  (Port 5173) │ ◀───────────────  │   (Port 8000)│
└──────────────┘                    └──────────────┘
        ▲                                   ▲
        └──────────── Docker Compose ──────┘

🌐 Application Endpoints
Service	URL
Frontend UI	http://localhost:3000

Backend API	http://localhost:8000/api/hello/

Django Admin	http://localhost:8000/admin/
🐳 Running with Docker (Recommended)
Prerequisites

Docker Desktop

Docker Compose (v2)

Start the application
docker compose up --build

Stop the application
docker compose down

⚙️ Local Development (Without Docker)
Backend (Django)
cd backend
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver


Backend available at:

http://localhost:8000/api/hello/

Frontend (React + Vite)
cd frontend
npm install
npm run dev


Frontend available at:

http://localhost:5173

🔁 CI/CD Pipeline

This repository includes a GitHub Actions workflow that:

Builds Docker images for frontend and backend

Validates Dockerfiles on every push

Ensures build consistency across environments

Workflow location:

.github/workflows/docker-build-push.yml

🔐 CORS Configuration

CORS is enabled in Django to allow secure communication between the React frontend and Django backend during both local development and containerized execution.

📸 Proof of Execution

The following were successfully verified:

✅ Frontend UI running

✅ Backend API responding (/api/hello/)

✅ Docker containers running simultaneously

✅ Docker Compose orchestration

✅ Django Admin accessible

✅ CI workflow present

Screenshots are provided as proof of execution.

🧠 DevOps Highlights

Fully Dockerized frontend and backend

Multi-container orchestration with Docker Compose

Clean and scalable repository structure

CI pipeline for automated Docker build validation

Environment consistency across systems

✅ Conclusion

This project successfully demonstrates practical DevOps skills by containerizing and orchestrating a full-stack application using industry-standard tools and workflows.
