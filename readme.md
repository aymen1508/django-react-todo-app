# Django + React Notes App

A simple full-stack notes application built with Django REST Framework on the backend and React + Vite on the frontend.

## Overview

This project demonstrates a basic CRUD-style notes app where:

- Django serves the API and handles database operations
- React renders a responsive UI for viewing and managing notes
- The app is wired together so the frontend can fetch data from the backend

## Tech Stack

- Backend: Python, Django, Django REST Framework
- Frontend: React, Vite, Tailwind CSS
- Database: SQLite
- API: REST endpoints for notes

## Project Structure

```bash
.
├── api/                  # Django REST API app
│   ├── models.py
│   ├── serializers.py
│   ├── urls.py
│   ├── views.py
│   └── migrations/
├── frontend-vite/        # React frontend
│   ├── src/
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
├── mynotes/              # Django project settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── db.sqlite3            # Local SQLite database
├── manage.py
├── requirements.txt
├── readme.md
└── assets/              # Collected static assets
```

## Features

- View all notes
- Open a single note
- Create, edit, and delete notes (depending on implementation status)
- REST API integration between Django and React
- Modern frontend using Vite and Tailwind CSS

## Prerequisites

Before running the app, make sure you have the following installed:

- Python 3.10+
- Node.js 18+
- npm

## Setup

### 1) Clone the repository

```bash
git clone https://github.com/aymen1508/django-react-todo-app.git
cd django-react-todo-app
```

### 2) Create and activate a virtual environment

On Windows:

```powershell
python -m venv env
env\Scripts\activate
```

On macOS/Linux:

```bash
python3 -m venv env
source env/bin/activate
```

### 3) Install Python dependencies

```bash
pip install -r requirements.txt
```

### 4) Apply database migrations

```bash
python manage.py migrate
```

### 5) Start the Django backend

```bash
python manage.py runserver
```

The backend will be available at:

```text
http://127.0.0.1:8000/
```

### 6) Start the React frontend

Open a second terminal window and run:

```bash
cd frontend-vite
npm install
npm run dev
```

The frontend dev server will typically run at:

```text
http://127.0.0.1:5173/
```

## API Endpoints

The Django app exposes notes endpoints under `/api`:

```text
GET /api/
GET /api/notes/
GET /api/notes/<id>/
```

## Production Notes

This project is set up to serve the built React app from Django templates, and the Django settings point to the `frontend-vite/dist` folder for static assets. For production deployments, build the frontend first:

```bash
cd frontend-vite
npm run build
```

Then run Django as usual.

## Notes

- The project uses SQLite for local development and quick setup.
- The frontend and backend are run separately in development mode.
- For production, you may want to configure environment variables, secure the Django secret key, and use a production-grade web server.

## License

This project is available for learning and development purposes.
