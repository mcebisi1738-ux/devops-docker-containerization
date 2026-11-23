# DevOps Project 4 – Docker Containerization

## Overview

This project demonstrates how to containerize a static HTML dashboard using Docker and Nginx Alpine. The application is packaged into a Docker image and deployed as a running container.

## Technology Stack

- Docker Engine
- Nginx Alpine
- HTML
- Dockerfile
- .dockerignore

## Project Structure

- `index.html` – Static web dashboard.
- `Dockerfile` – Defines how the Docker image is built.
- `.dockerignore` – Excludes unnecessary files from the Docker build context.

## Docker Implementation

The Dockerfile uses `nginx:alpine` as a lightweight base image.

- `FROM nginx:alpine` – Selects the Nginx Alpine base image.
- `COPY index.html /usr/share/nginx/html/index.html` – Copies the dashboard into Nginx's web directory.
- `EXPOSE 80` – Documents the port used by Nginx inside the container.

## Build and Run

Build the Docker image:

```bash
docker build -t devops-docker-containerization:v1 .
```

Run the container:

```bash
docker run -d --name devops-docker-containerization -p 8081:80 devops-docker-containerization:v1
```

Access the application:

`http://localhost:8081`

## Verification

The application was tested using:

```bash
docker ps
curl http://localhost:8081
```

The dashboard was successfully served through the running Docker container.

## Learning Outcomes

- Understanding Docker images and containers.
- Writing and understanding Dockerfiles.
- Using lightweight base images.
- Managing Docker build contexts with `.dockerignore`.
- Building and tagging Docker images.
- Running containers in detached mode.
- Publishing container ports to the host machine.
- Verifying container status and application availability.