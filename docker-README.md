# Todo App - Flask + ReactJS (Dockerized)

A full-stack **Todo Application** with user authentication, built with **Flask** (Python backend) and **React + TypeScript** (Vite frontend).  

This is my forked and improved version of the original project by [Remy349](https://github.com/Remy349/todo-app-flask-reactjs), where I focused on **containerization** using **Docker** and **Docker Compose**.

##  Features

- User registration and login with **JWT authentication**
- Create, Read, Update, and Delete (CRUD) tasks and tags
- Modern React frontend with TypeScript, TailwindCSS, ShadcnUI, Zustand, and React Query
- REST API built with Flask, SQLAlchemy, and Flask-Smorest
- Swagger UI for API documentation (`/docs`)
- Fully containerized setup – one command to run everything

##  Quick Start (Recommended)

Make sure you have **Docker** and **Docker Compose** installed.

```bash
git clone https://github.com/Basima-dev/todo-app-flask-reactjs.git
cd todo-app-flask-reactjs

# Build and start the app
docker compose up --build

```
Once the containers are running, open your browser and visit:→ http://localhost:5173The frontend will communicate with the backend automatically.
Note: The first time you run it, Docker will build both the frontend and backend images.
**Technologies**
Backend:Python 3.10 + Flask
SQLAlchemy + Flask-SQLAlchemy + Flask-Migrate
Flask-JWT-Extended (Authentication)
Flask-Smorest (REST API + Swagger)

Frontend:React + TypeScript
Vite
TailwindCSS + ShadcnUI
Axios, React Router Dom, React Hook Form, Zustand, React Query

DevOps:Docker
Docker Compose

 Project Structure
<details open>
todo-app-flask-reactjs/
├── frontend/          # Vite + React + TypeScript
│   └── Dockerfile
├── backend/           # Flask + Python
│   ├── Dockerfile
│   ├── requirements.txt
│   └── ...
├── docker-compose.yaml
└── README.md
</details>

**Docker Setup Details**
I made the following improvements for smooth containerization:
Frontend: Fixed Vite dev server to listen on all interfaces (--host 0.0.0.0)
Backend: Configured Flask to run on 0.0.0.0:5000 using environment variables in docker-compose.yaml
Added proper port mapping:Frontend → 5173
Backend → 5000

Available Docker Commandsbash
```bash

# Start the app (recommended)
docker compose up --build

# Run in background
docker compose up -d --build

# View logs
docker compose logs -f

# Stop containers
docker compose down
```

**What I Learned**
This was my first time working with a Flask backend.
I faced (and solved) these common Docker issues:Vite not accessible from the browser → Fixed with --host 0.0.0.0
Flask only binding to localhost inside container → Fixed using FLASK_RUN_HOST=0.0.0.0 in docker-compose

Everything now works perfectly with just docker compose up --build.
**Original ProjectThis is a fork of the excellent todo app by Remy349:Original Repository: https://github.com/Remy349/todo-app-flask-reactjs**

**Notes**
This setup is optimized for local development.
The app uses SQLite (no external database required).
For production, consider using a proper WSGI server (Gunicorn) and a robust database.

Happy coding!   Feel free to star the repo if you find it useful, and contributions are welcome!


