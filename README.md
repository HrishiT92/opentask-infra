# OpenTask Infrastructure

This repository contains the Docker Compose configuration and infrastructure setup for the OpenTask project.

## Prerequisites

Before running the infrastructure, you need to clone all the required repositories:

```bash
mkdir opentask-project
cd opentask-project

git clone https://github.com/HrishiT92/opentask-backend.git
git clone https://github.com/HrishiT92/opentask-frontend.git
git clone https://github.com/HrishiT92/opentask-infra.git
git clone https://github.com/HrishiT92/opentask-docs.git
```

## Directory Structure

After cloning, your directory structure should look like:

```
opentask-project/
├── opentask-backend/     # .NET 8 Web API
├── opentask-frontend/    # React 18 + TypeScript
├── opentask-infra/       # Docker Compose (this repo)
└── opentask-docs/        # Documentation
```

## Running the Application

1. Navigate to the infrastructure directory:
   ```bash
   cd opentask-infra
   ```

2. Start all services:
   ```bash
   docker compose up -d
   ```

3. Access the application:
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000
   - Swagger UI: http://localhost:5000
   - pgAdmin: http://localhost:5050 (admin@opentask.com / admin123)
   - MinIO Console: http://localhost:9001 (opentask / opentask123)

## Services

- **PostgreSQL**: Database server on port 5432
- **pgAdmin**: Database administration tool on port 5050
- **MinIO**: S3-compatible object storage on ports 9000/9001
- **Backend**: .NET 8 Web API on port 5000
- **Frontend**: React application on port 3000

## Environment Variables

The Docker Compose file includes default environment variables for development. For production deployment, create a `.env` file with appropriate values.

## Stopping the Application

```bash
docker compose down
```

To remove volumes as well:
```bash
docker compose down -v
```
