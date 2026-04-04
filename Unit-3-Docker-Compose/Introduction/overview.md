# Microservices with Docker Compose

## Overview
This project demonstrates how to build and deploy **Microservices Architecture** using **Docker Compose**. It shows how multiple services such as frontend, backend, and database can run together using containers while maintaining isolation, scalability, and easy deployment.

Docker Compose simplifies managing multi-container applications by defining services, networks, and volumes in a single **docker-compose.yml** file.

---

# 1. Microservices Architecture

## What are Microservices?
Microservices is an architectural style where an application is divided into **small independent services** that communicate with each other using APIs.

Each microservice:
- Runs independently
- Has its own resources or database
- Can be deployed and scaled separately

---

## Need for Microservices

Traditional applications often become large and difficult to maintain. Microservices solve this by:

- Breaking large systems into smaller services
- Allowing independent deployment
- Improving fault isolation
- Supporting faster development and updates

---

## Monolithic vs Microservices

| Feature | Monolithic Architecture | Microservices Architecture |
|--------|-------------------------|-----------------------------|
| Structure | Single large application | Multiple small services |
| Deployment | Entire app deployed together | Services deployed independently |
| Scalability | Hard to scale individual components | Easy to scale specific services |
| Fault Isolation | Failure affects entire system | Failure limited to one service |
| Development | Slower for large teams | Faster parallel development |

---

# 2. Advantages of Microservices

## Scalability
Each service can be scaled independently depending on the workload.

Example:
- Backend API can scale during heavy traffic.
- Database service can be scaled separately.

---

## Isolation
If one service fails, other services continue running.

Example:
If the payment service crashes, the rest of the application remains functional.

---

## Agility
Different teams can develop different services simultaneously.

Example:
- Frontend → React
- Backend → Node.js
- Database → MongoDB

---

## API Gateway
An **API Gateway** acts as a single entry point for all client requests. It routes requests to the appropriate microservice.

Benefits:
- Centralized authentication
- Request routing
- Rate limiting
- Security management

---

# 3. Docker Compose

Docker Compose is a tool used to define and run **multi-container Docker applications** using a YAML configuration file.

---

## YAML Structure

A typical `docker-compose.yml` file contains:

- version
- services
- volumes
- networks

---

## Example docker-compose.yml

```yaml
version: "3.9"

services:

  frontend:
    image: nginx
    ports:
      - "80:80"

  backend:
    build: ./backend
    ports:
      - "5000:5000"
    depends_on:
      - database

  database:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: appdb
```

---

# 4. Important Docker Compose Concepts

## Version
Defines the version of Docker Compose syntax used.

Example:

```yaml
version: "3.9"
```

---

## Services
Services define the containers that will run in the application.

Example:

```yaml
services:
  web:
    image: nginx
```

---

## Volumes
Volumes are used to store persistent data even if containers are removed.

Example:

```yaml
volumes:
  db_data:
```

---

## Networks
Networks allow containers to communicate with each other.

Example:

```yaml
networks:
  app_network:
```

---

## Environment Variables
Environment variables allow configuration values to be passed to containers.

Example:

```yaml
environment:
  - MYSQL_ROOT_PASSWORD=root
```

---

## Secrets and Configs
Secrets are used to store sensitive information such as passwords or API keys securely.

Example:

```yaml
secrets:
  db_password:
    file: ./db_password.txt
```

---

## Build vs Image

### Image
Uses an existing image from Docker Hub.

```yaml
image: nginx
```

### Build
Builds an image from a Dockerfile.

```yaml
build: .
```

---

## Service Dependency Ordering

Docker Compose allows services to start in a specific order using **depends_on**.

Example:

```yaml
depends_on:
  - database
```

---

# 5. Use Case Deployments

## WordPress + MySQL

Example setup:

- WordPress container
- MySQL container
- Persistent database storage

---

## Node.js + MongoDB

Typical microservice stack:

- Node.js backend
- MongoDB database
- API communication between services

---

## Java Spring Boot + PostgreSQL

Enterprise application architecture:

- Spring Boot backend service
- PostgreSQL database
- Docker Compose manages the containers

---

# 6. Running the Application

### Build and Start Containers

```bash
docker-compose up --build
```

---

### Run Containers in Background

```bash
docker-compose up -d
```

---

### Stop Containers

```bash
docker-compose down
```

---

# Conclusion

Docker Compose simplifies deployment of **microservice-based applications** by managing multiple containers in a single configuration file. It improves scalability, maintainability, and development speed for modern distributed systems.
