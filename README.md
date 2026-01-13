# Task Management System (Kanban Based)

## Project Overview

This is a full-stack **Task Management System** built using the **Kanban methodology**.
The application allows authenticated users to manage tasks visually across different stages — **Pending**, **In-Progress**, and **Completed** — using a drag-and-drop interface.

Each user has their own private task board. Tasks can be created, updated, deleted, and moved between columns, with all changes persisted to the backend.

The project focuses on:

- Clean and maintainable code
- Proper folder structure
- End-to-end functionality
- Secure authentication
- Minimal, professional UI

---

## 🛠 Tech Stack Used

### Frontend

- React (Vite)
- React Router DOM
- Axios
- @hello-pangea/dnd (Drag & Drop)
- CSS (custom, no UI framework)

### Backend

- Node.js
- Express.js
- MongoDB (MongoDB Atlas)
- Mongoose
- JSON Web Token (JWT)
- bcryptjs

---

## Project Structure

```text
Ozi-Project/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── utils/
│   │   └── app.js
│   ├── server.js
│   ├── .env
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── api/
│   │   ├── auth/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── styles/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── .env
│   └── package.json
│
└── README.md
```

---

## Authentication & User Management

- User registration and login using JWT
- Secure token storage in browser
- Protected routes (cannot access board/profile without login)
- Logout functionality
- Profile management:
  - Update name
  - Update email
  - Update password
  - Delete account

---

## Task Management Features

Each task contains:

- **Title**
- **Short description**
- **Status** (`pending`, `in-progress`, `completed`)
- **Due date**
- **Created timestamp**

### Functionalities:

- Create tasks using a modal form
- Assign status at creation
- Drag & drop tasks between columns
- Status updates persist via backend API
- Delete tasks
- Tasks are user-specific
- Tasks fetched from backend based on status

---

## Kanban Board

The board consists of three columns:

1. Pending
2. In-Progress
3. Completed

Tasks are displayed as cards and can be dragged between columns to update their status.

---

## Backend Setup Instructions

### 1️ Navigate to backend folder

`cd backend`

---

### 2 Install dependencies

`npm install`

### 3 Create `.env` file

`PORT=5000`
`MONGO_URI=your_mongodb_atlas_connection_string`
`JWT_SECRET=your_secret_key`
`JWT_EXPIRES_IN=1d`

### 4 Start backend server

`npm run dev`

Server will run at:
`http://localhost:5000`

---

## Frontend Setup Instructions

### 1 Navigate to frontend folder

`cd frontend`

### 2 Install dependencies

`npm install`

### 3 Create `.env` file

`VITE_API_BASE_URL=http://localhost:5000/api`

### 4 Start frontend server

`npm run dev`

Frontend will run at:
`http://localhost:5173`

---

## Environment Variables Summary

### Backend (`backend/.env`)

| Variable       | Description                     |
| -------------- | ------------------------------- |
| PORT           | Backend server port             |
| MONGO_URI      | MongoDB Atlas connection string |
| JWT_SECRET     | Secret key for JWT              |
| JWT_EXPIRES_IN | Token expiry duration           |

### Frontend (`frontend/.env`)

| Variable          | Description          |
| ----------------- | -------------------- |
| VITE_API_BASE_URL | Backend API base URL |

---

## API Overview

### Auth Routes

`POST /api/auth/register` – Register user
`POST /api/auth/login` – Login user

### User Routes (Protected)

`GET /api/user` – Get profile
`PUT /api/user` – Update profile
`DELETE /api/user` – Delete account

### Task Routes (Protected)

`POST /api/tasks` – Create task
`GET /api/tasks` – Get all tasks
`GET /api/tasks?status=pending` – Filter tasks by status
`PUT /api/tasks/:id` – Update task
`DELETE /api/tasks/:id` – Delete task

# Screenshots

![1768320454473](image/README/1768320454473.png)

![1768320514697](image/README/1768320514697.png)
