# Task Management System

A REST API for managing users, tasks, comments, attachments, notifications, and audit logs.

## Technologies

- Python
- FastAPI
- PostgreSQL
- SQLAlchemy
- Pydantic
- JWT Authentication
- Alembic
- Pytest
- Postman

## Features

- User Registration and Login
- JWT Authentication
- Admin/User Role-Based Access Control
- User Management
- Task CRUD and Assignment
- Task Priority and Status Management
- Comments
- File Attachments
- Notifications
- Audit Logs
- Dashboard and Reports
- Search, Filter, Sort and Pagination
- Business Rule Validation

## Project Structure

    Task_Managament_System/
    ├── app/
    ├── alembic/
    ├── tests/
    ├── uploads/
    ├── postman/
    ├── README.md
    ├── requirements.txt
    ├── alembic.ini
    ├── .env.example
    └── .gitignore

## Database

Database: PostgreSQL

Database name:

    task_management

Run migrations:

    alembic upgrade head

## Installation

Create and activate the virtual environment, then install dependencies:

    pip install -r requirements.txt

Configure the database and application settings using `.env`.

## Run the Application

    python -m uvicorn app.main:app --reload

Application:

    http://127.0.0.1:8000

Swagger API Documentation:

    http://127.0.0.1:8000/docs

## Authentication

The system uses JWT authentication.

Users can:

- Register
- Login
- View Profile
- Update Profile
- Change Password
- Logout

## Roles

### Admin

- Manage users
- Create, update and delete users
- Activate/deactivate users
- Manage all tasks
- View audit logs
- View admin dashboard

### User

- Create tasks
- View assigned tasks
- Update permitted tasks
- Change task status and priority
- Add comments
- Upload attachments
- View notifications
- View personal dashboard

## Task Management

Task priorities:

- Low
- Medium
- High
- Critical

Task statuses:

- Todo
- In Progress
- Completed
- Cancelled

The system validates task status transitions and prevents modification of completed or cancelled tasks.

## Comments

Users can:

- Create comments
- View comments
- Update their own comments
- Delete their own comments

Completed and cancelled tasks cannot receive new comments.

## Attachments

Supported file types:

- PDF
- PNG
- JPG
- JPEG
- TXT
- DOC
- DOCX
- XLS
- XLSX
- CSV

Maximum file size: **5 MB**

## Notifications

Notifications are generated for events such as:

- Task assignment
- Task reassignment
- Status changes
- Comments
- Task completion

Users can view, read and delete their notifications.

## Audit Logs

Important task and user actions are recorded in audit logs.

Admin users can view audit records through the API.

## Dashboard

The project provides:

- Admin dashboard
- Personal user dashboard
- Task status statistics
- Task priority statistics
- User statistics
- Overdue task information

## Testing

Run automated tests:

    pytest

Test result:

**32 tests collected — 31 passed, 1 skipped.**

Postman was also used for manual API testing.

## Postman

The `postman/` folder contains the exported Postman collection and environment used for API testing.

## API Documentation

FastAPI automatically provides interactive Swagger documentation:

    http://127.0.0.1:8000/docs

## Project Architecture

    Client
       ↓
    FastAPI Routers
       ↓
    Pydantic Schemas
       ↓
    Service Layer
       ↓
    Repository Layer
       ↓
    SQLAlchemy ORM
       ↓
    PostgreSQL

## Conclusion

This project implements a complete Task Management REST API with authentication, RBAC, task management, comments, attachments, notifications, audit logging, dashboards, validation, and automated testing.
