# GitHub Container Registry (GHCR) – Docker Demo 🚀

This project demonstrates how to:
- ✔ Build a Docker image
- ✔ Push a Docker image to GitHub Container Registry (GHCR)
- ✔ Pull the image from GHCR
- ✔ Authenticate Docker using GitHub Personal Access Token (PAT)

---

## 🔐 GitHub Personal Access Token (PAT)

### Step 1 → Open Token Settings
Go to:
GitHub → Settings → Developer Settings → Personal Access Tokens

Direct link:
https://github.com/settings/tokens

---

### Step 2 → Generate Token
- Select **Classic Token**
- Enable permissions:
  - ✔ `write:packages`
  - ✔ `read:packages`
  - ✔ `delete:packages` (optional)

---

### Step 3 → Copy Token
⚠️ Important:
- Copy the token immediately
- You will NOT be able to view it again

💡 **Tip:**  
GitHub PAT acts as a **Docker password**, NOT your GitHub account password.

---

## 📦 Create Simple Demo Project

### Step 1 → Create Project Folder
```bash
mkdir ghcr-demo
cd ghcr-demo
```
### Step 2 → Create Dockerfile
```bash
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
```
### Step 3 → Create index.html
```bash
<h1>GHCR Demo Success 🎉</h1>
```
### Step 4 → 🛠 Build Docker Image
```bash
docker build -t ghcr.io/yourusername/ghcr-demo .
```
### Step 5 → Push Image to GHCR
```bash
docker push ghcr.io/yourusername/ghcr-demo
```
## ✅ Conclusion

This project successfully demonstrates the complete workflow of using Docker with GitHub Container Registry (GHCR). Starting from building a Docker image locally, the image was authenticated using a GitHub Personal Access Token (PAT), pushed securely to GHCR, and then pulled back to verify successful storage and retrieval. Finally, the container was executed locally to confirm correct deployment.

Through this demo, key concepts such as containerization, image registry management, and secure authentication were clearly understood. This process reflects a real-world DevOps workflow and serves as a strong foundation for deploying containerized applications using GitHub and Docker.
