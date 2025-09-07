
# Me-API Playground

Me-API Playground is a lightweight API-driven application designed to showcase a candidate’s profile, projects, skills, and professional journey in an interactive way. Instead of a static resume, this project provides a live API and minimal frontend where anyone can search and explore details such as skills, projects, and background.

This is a self-hosted personal playground that combines a backend API, a database, and a basic frontend UI into a single deployable project. It has been adapted with real-world data for Krishna Modani, making it both a personal portfolio API and a demonstration of full-stack development skills.


## Features

#### Backend (FastAPI)

- CRUD operations on profile (name, email, education, skills, projects, work experience, links).

- Query endpoints for searching projects by skill, retrieving top skills, and global text search.

- Health check endpoint at /health.

#### Database (SQLite with SQLAlchemy ORM)

- Profiles, Skills, Projects, Work Experience, and Links stored in relational tables.

- Pre-seeded with real candidate data.

- Can be easily migrated to PostgreSQL/MySQL if required.

#### Frontend (React)

- Minimal and clean UI for:

  - Viewing profile details

  - Listing projects

  - Searching by skill

- Communicates with backend API (CORS enabled).

#### Deployment Ready

- Fully containerized with Docker and Docker Compose.

- Can be hosted locally or on platforms like Render, Railway, or Vercel (without AWS dependency).


## Getting Started

#### Prerequisites

- Python 3.10+
- Node.js 16+
- Git installed
- (Optional) Docker & Docker Compose

#### Running Locally
- Clone the repository:    
```bash
  git clone https://github.com/krishnamodani/me-api-playground.git
  cd me-api-playground
```
- Backend setup:
```bash
  cd backend
  pip install -r requirements.txt
  python app/seed.py    # Seed the database
  uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```
Backend will now run at: http://localhost:8000

- Frontend setup:
```bash
  cd frontend
  npm install
  npm start
```
Frontend will now run at: http://localhost:3000

- Verify:
  - http://localhost:8000/health → should return { "status": "ok" }

  - http://localhost:3000 → should load your UI
## API Reference

Candidate profile details:
```bash
  GET /profile
```
Add a profile (auth can be added):
```bash
  POST /profile
```
Update profile:
```bash
  PUT /profile
```
List all projects:
```bash
  GET /projects
```
Filter projects by skill:
```bash
  GET /projects?skill=python
```
Get top skills:
```bash
  GET /skills/top
```
Search across profile, skills, and projects:
```bash
  GET /search?q=AI
```
Health check:
```bash
  GET /health
```

## Authors

- [Github @krishnamodani](https://www.github.com/krishnamodani)
- [LinkedIn @Krishna Modani](https://www.linkedin.com/in/krishna-modani/)
- [Resume](https://drive.google.com/file/d/1dtOnxRyl1bydvmTtIAxaIZZVAP2Sklzn/view)
