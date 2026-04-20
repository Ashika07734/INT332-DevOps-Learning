# 🛠️ Jenkins Installation Guide

This document provides step-by-step instructions to install Jenkins and configure the basic environment required to run Jenkins pipelines.

Jenkins is a widely used Continuous Integration (CI) and Continuous Deployment (CD) tool that automates software development workflows.

---

# 📋 Prerequisites

Before installing Jenkins, ensure the following software is installed:

- Java Development Kit (JDK 17 or above)
- Web Browser (Chrome / Edge / Firefox)
- Git (for repository integration)
- Docker 

---

# ⚙️ Step 1 – Install Java (JDK)

Jenkins requires Java to run.

Check Java installation:

```bash
java -version
```
# If Java is not installed:

- Download JDK 17 or above
- Install Java
- Set JAVA_HOME environment variable
- Add Java to system PATH
---

# ⚙️ Step 2 – Download Jenkins

Download Jenkins from the official website:
```bash
https://www.jenkins.io/download/
```
Choose:
- Windows (.msi installer) for Windows users
- Generic Java Package (.war) for manual setup
---

# ⚙️ Step 3 – Install Jenkins (Windows MSI Method)
- Run Jenkins installer (.msi file)
- Follow installation wizard
- Choose default installation settings
- Jenkins installs as a Windows service
- Default port used:
8080

- After installation, Jenkins starts automatically.
---
# ⚙️ Step 4 – Access Jenkins Dashboard

Open browser and enter:
```bash
http://localhost:8080
```
- Jenkins will ask for an Administrator Password.
---
# ⚙️ Step 5 – Unlock Jenkins

Find initial password from:
```bash
C:\Program Files\Jenkins\secrets\initialAdminPassword
```
Steps:

- Open the file
- Copy password
- Paste into Jenkins browser page
- Click Continue
---
# ⚙️ Step 6 – Install Recommended Plugins

After unlocking Jenkins:

Select:
Install suggested plugins

These plugins include:

- Git Plugin
- Pipeline Plugin
- Maven Integration Plugin
- Docker Plugin
- GitHub Plugin

Wait until installation completes.

---
# ⚙️ Step 7 – Create Admin User

After plugin installation:

Create Jenkins admin user
- Enter:
- Username
- Password
- Email

Click:

Save and Continue

Jenkins setup completes.

---
# ⚙️ Step 8 – Verify Jenkins Installation

Open:
```bash
http://localhost:8080
```
You should see:

Jenkins Dashboard

This confirms successful installation.

---

# ⚙️ Step 9 – Install Required Tools in Jenkins

Go to:

Manage Jenkins → Global Tool Configuration

Install:

Maven

Add Maven tool:

Name: Maven
Install automatically: ✓
Version: Latest
Git

Ensure Git path is configured.

JDK

Add Java installation if required.

# ⚙️ Step 10 – Install Additional Plugins (Optional)

Go to:

Manage Jenkins → Plugin Manager

Install useful plugins:

- Docker Plugin
- GitHub Integration Plugin
- Pipeline Plugin
- Blue Ocean Plugin
- Maven Integration Plugin

Restart Jenkins after plugin installation.

---
---

## ⭐ Importance of Jenkins Installation

Installing Jenkins is essential for setting up automated CI/CD pipelines.

The importance includes:

- Enables automated builds and testing  
- Supports continuous integration workflows  
- Reduces manual deployment errors  
- Improves development productivity  
- Enables integration with GitHub and Docker  
- Supports automated deployment pipelines  
- Improves software delivery speed  

Proper Jenkins installation ensures a stable environment for running automation workflows.

---

## ✅ Conclusion

Jenkins installation is the first step toward implementing automated CI/CD pipelines.

After completing the installation:

- Jenkins server becomes available  
- Plugins enable integration with development tools  
- Maven and Docker tools can be configured  
- Automated build and deployment workflows can be created  

This setup forms the foundation for implementing Continuous Integration and Continuous Deployment in modern DevOps environments.

---
