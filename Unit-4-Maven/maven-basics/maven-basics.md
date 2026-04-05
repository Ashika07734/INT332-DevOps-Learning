# 📌 Basic Commands – Maven & Docker

This document contains commonly used Maven and Docker commands required to build, package, and run applications in Unit-4.

These commands help automate project builds and container execution.

---

# 📦 Maven Basic Commands

## Check Maven Version

```bash
mvn -version
```
## Validate Project
```bash
mvn validate
```
Checks whether project structure and configuration are correct.

## Compile Project
```bash
mvn compile
```
Compiles the source code of the project.

## Run Unit Tests
```bash
mvn test
```
Runs test cases using the Surefire plugin.

## Package Project
```bash
mvn package
```
Creates JAR/WAR file inside:
```bash
target/
```

## Install Project
```bash
mvn install
```
Installs the package into the local Maven repository.

## Clean Project
```bash
mvn clean
```
Removes previously generated files.

## Clean and Build Project
```bash
mvn clean package
```
Most commonly used command for building the project.

## Build Docker Image
```bash
docker build -t maven-app .
```
Builds Docker image from Dockerfile.

## Run Docker Container
```bash
docker run -p 8080:8080 maven-app
```
Runs container and maps port 8080.

## List Running Containers
```bash
docker ps
```
Displays currently running containers.

## List All Containers
```bash
docker ps -a
```
Displays all containers (running and stopped).

---

## ⭐ Importance of Basic Commands

Basic Maven and Docker commands are essential for performing build automation and container management tasks efficiently.

The importance of these commands includes:

- Helps automate **compilation and packaging** of Java applications  
- Enables **unit testing** of projects using Maven  
- Supports creation of **JAR/WAR files** automatically  
- Allows building **Docker images** from application files  
- Enables running applications inside **isolated containers**  
- Improves **productivity and development speed**  
- Reduces chances of **manual errors**  
- Ensures a **consistent build and execution environment**

Understanding these commands is important for managing projects effectively in modern DevOps environments.

---

## ✅ Conclusion

Basic Maven and Docker commands play a significant role in building, testing, packaging, and running applications.

After learning these commands:

- Developers can **build projects automatically**  
- Applications can be **packaged into executable files**  
- Docker containers can be used to **run applications reliably**  
- Projects become easier to **deploy and manage**  
- The development workflow becomes suitable for **DevOps practices**

These commands form the foundation for working with Maven-based applications and containerized environments in Unit-4.

---
