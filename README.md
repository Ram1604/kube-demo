# kube-demo

# 📘 VIM Quick Reference Guide

Vim is a powerful text editor available on most UNIX systems. Below is a concise guide to get started and be productive.

---

## 📝 Modes in Vim

## Vim has **three primary modes**:

| Mode    | Description                          |
|---------|--------------------------------------|
| Normal  | Default mode for navigation & editing |
| Insert  | For inserting text                   |
| Command | For saving, quitting, etc.           |

---

## 🚀 Getting Started

### Open/Create a File
```bash
vim filename
```

### ✍️ Insert Mode

| Key | Action            |
| --- | ----------------- |
| `i` | Enter Insert Mode |

### ⌨️ Return to Normal Mode

| Key   | Action                |
| ----- | --------------------- |
| `ESC` | Return to Normal mode |

### ✂️ Editing in Normal Mode

| Key      | Action              |
| -------- | ------------------- |
| `x`      | Delete character    |
| `dd`     | Delete current line |
| `yy`     | Copy (yank) line    |
| `p`      | Paste below         |
| `P`      | Paste above         |
| `u`      | Undo                |
| `Ctrl+r` | Redo                |

### 💾 Save & Quit

| Command | Description         |
| ------- | ------------------- |
| `:w`    | Save                |
| `:q`    | Quit                |
| `:wq`   | Save and quit       |
| `:q!`   | Quit without saving |

### 🔄 Navigation

| Key | Action     |
| --- | ---------- |
| `h` | Move left  |
| `j` | Move down  |
| `k` | Move up    |
| `l` | Move right |

<br>

<br>

# 🐳 Docker Quick Reference Guide
### Working with Docker is essential when building, shipping, and running applications in containers. Below is a quick guide to using Docker with your own application.

### 🔐 Step 1: Login to Docker Hub
```bash
docker login
```

### 🛠️ Step 2: Build Your Docker Image
#### Make sure your Dockerfile is ready and then run:
```bash
docker build -t yourdockerhubusername/repo_name:latest .
```
#### Replace yourdockerhubusername/repo_name with your actual Docker Hub username and repository name.

### 🚀 Step 3: Push Your Docker Image

```bash
docker push yourdockerhubusername/repo_name:latest
```
<br>


<br>

# ☸️ Kubernetes (Minikube) Quick Reference Guide

Use Kubernetes with Minikube to run and expose containerized applications locally.

---

## 📦 Step 1: Apply the Deployment Configuration

Use a YAML manifest to create a deployment:

```bash
kubectl apply -f deployment.yaml
```
## 🌐 Step 2: Expose the Deployment

```bash
kubectl expose deployment deployment-name --type=NodePort --port=5000
```
#### --port=5000 should match your container/app port.

## 🚀 Step 3: Access the App via Minikube

```bash
minikube service myapp-deployment --url
```
#### This will open the app in your default browser or show a URL to access it.


## 🐳 Pull Docker Image from DockerHub and Push to Google Artifact Registry to deploy it in GKE

### 1. ✅ Create a Docker Repository in Artifact Registry

```bash
gcloud artifacts repositories create REPO_NAME \
  --repository-format=docker \
  --location=us-central1 \
  --description="Docker repository"
```
### 2. 🔐 Authenticate Docker to Artifact Registry

```bash
gcloud auth configure-docker us-central1-docker.pkg.dev
```

### 3. 📥 Pull the Docker Image from DockerHub

```bash
docker pull DOCKERHUB_USERNAME/IMAGE_NAME:TAG
```

### 4. 🔍 Verify the Image Exists Locally

```bash
docker images
```

### 5. 🏷️ Tag the Image for Artifact Registry

```bash
docker tag DOCKERHUB_USERNAME/IMAGE_NAME:TAG \
  us-central1-docker.pkg.dev/PROJECT_ID/REPO_NAME/IMAGE_NAME:TAG
```
### 6. 🚀 Push the Image to Artifact Registry

```bash
docker push us-central1-docker.pkg.dev/PROJECT_ID/REPO_NAME/IMAGE_NAME:TAG
```