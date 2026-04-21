# Module 12 – User & Calculation Routes + Integration Testing

## Overview

This project implements a FastAPI backend with:

- User authentication (register + login)
- Calculation CRUD operations (BREAD)
- PostgreSQL database integration
- Docker containerization
- Integration testing with pytest
- CI/CD pipeline using GitHub Actions

---

##  Running the Application

### Start the application using Docker

```bash
docker compose up --build 
Access API Documentation
Swagger UI: http://localhost:8000/docs
ReDoc: http://localhost:8000/redoc
Running Integration Tests

Run tests inside the Docker container:

docker compose exec web pytest tests/integration -v

All tests pass successfully.

 User Endpoints
Authentication Routes
POST /auth/register – Register user
POST /auth/login – Login with JSON
POST /auth/token – Login (form-based for Swagger)
Assignment Routes (Aliases)
POST /users/register – Register user
POST /users/login – Login user
 Calculation Endpoints (BREAD)
POST /calculations – Add calculation
GET /calculations – Browse calculations
GET /calculations/{id} – Read calculation
PUT /calculations/{id} – Update calculation
DELETE /calculations/{id} – Delete calculation
 Authentication
Uses token-based authentication (JWT)
Protected endpoints require authorization via Swagger “Authorize” button
 Database
PostgreSQL runs in Docker container
pgAdmin available at:
http://localhost:5050
pgAdmin Login
Email: admin@example.com
Password: admin
 Docker Hub

https://hub.docker.com/r/ssingh1119/module12_is601

⚙️ CI/CD Pipeline

GitHub Actions is configured to:

Run integration tests automatically
Build Docker image
Ensure application stability before deployment

 Reflection

In this assignment, I implemented user authentication and calculation CRUD operations using FastAPI and PostgreSQL. A major challenge I encountered was configuring the testing environment. Initially, integration tests failed due to database connection issues because PostgreSQL was running inside Docker while tests were executed locally.

I resolved this by running tests inside the Docker container, ensuring the application and database shared the same network environment. This aligned my local setup with the CI/CD pipeline and prevented connection errors.

Another challenge was dependency compatibility, particularly with psycopg2 and Python versions. Switching to a supported Python version resolved installation issues and allowed tests to run successfully.

Through this assignment, I gained hands-on experience with API development, database integration, containerization, and automated testing. It also reinforced the importance of consistent environments across development and deployment workflows.