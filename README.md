# FastAPI Docker Application

A structured, production-ready template for deploying a FastAPI backend using Docker and Docker Compose. This setup utilizes a minimal Python environment for optimized builds and fast startup times.

## 🚀 Quick Start

### 1. Build and Run
Start the application using Docker Compose. This command builds the image and maps the necessary ports.

```bash
docker compose up --build
```

### 2. Access the API
Once the container is running, access the following local endpoints:
- **API Base URL:** [http://localhost:8000](http://localhost:8000)
- **Swagger UI (Interactive Docs):** [http://localhost:8000/docs](http://localhost:8000/docs)
- **ReDoc (Alternative Docs):** [http://localhost:8000/redoc](http://localhost:8000/redoc)

### 3. Stop the Service
To cleanly shut down the application and remove the container network:

```bash
docker compose down
```

## 🛠️ Project Structure

```text
.
├── app.py                 # Main FastAPI application
├── requirements.txt       # Python dependencies (FastAPI, Uvicorn)
├── Dockerfile             # Optimized Docker build instructions
└── docker-compose.yml     # Docker Compose configuration
```

## 🐳 Docker Configuration Details

- **Base Image:** Optimized Python 3.12 slim image.
- **Dependency Management:** Dependencies are copied and installed prior to the application code to leverage Docker layer caching, significantly speeding up rebuilds.
- **Server:** Runs via `uvicorn` mapped to host port `8000`.

## 📦 Container Registry Deployment

To push this image to a container registry (e.g., Docker Hub) for sharing or deployment:

```bash
# 1. Log in to your registry
docker login

# 2. Tag the image
docker tag fast-api-demo-server <your-username>/fast-api-demo-server:latest

# 3. Push the image
docker push <your-username>/fast-api-demo-server:latest
```