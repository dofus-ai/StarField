# StarField

A simple containerized app that can be run either:

1. with plain Docker from the command line,  
2. through an ONCE-style installation flow.

---

## 🚀 Requirements

### Docker
Make sure Docker is installed:

https://docs.docker.com/get-docker/

### ONCE (optional)
If you are using ONCE-style deployment, ensure your install script and environment are set up.

---

## 🐳 Run with Docker (Local)

### 1. Clone the repository

```bash
git clone https://github.com/dofus-ai/StarField.git
cd StarField
```

### 2. Build the Docker image

```bash
docker build -t starfield:latest .
```

### 3. Run the container

```bash
docker run --rm -p 8080:80 starfield:latest
```

Open your browser:

http://localhost:8080

---

### Run in background

```bash
docker run -d --name starfield -p 8080:80 starfield:latest
```

### Stop the container

```bash
docker stop starfield
```

---

## 📦 Run from GitHub Container Registry (GHCR)

If the image is already published:

```bash
docker pull ghcr.io/dofus-ai/starfield:latest
docker run --rm -p 8080:80 ghcr.io/dofus-ai/starfield:latest
```

Run a specific version:

```bash
docker pull ghcr.io/dofus-ai/starfield:v2
docker run --rm -p 8080:80 ghcr.io/dofus-ai/starfield:v2
```

---

## 🔁 Update the App

After making changes:

```bash
git add .
git commit -m "Update app"
git push origin main
```

Then rebuild and push a new container:

```bash
docker build -t ghcr.io/dofus-ai/starfield:latest .
docker push ghcr.io/dofus-ai/starfield:latest
```

Or versioned:

```bash
docker build -t ghcr.io/dofus-ai/starfield:v2 .
docker push ghcr.io/dofus-ai/starfield:v2
```

---

## ⚡ Run with ONCE

Use this only if you have packaged this app for ONCE-style deployment.

### Install

Run your install script on your server:

```bash
/bin/bash -c "$(curl -fsSL YOUR-ONCE-INSTALL-URL)"
```

This typically:
- installs Docker
- pulls your container
- configures domain + SSL

---

### Manage the app

```bash
once
```

Use this command to access admin tasks like updates, backups, etc.

---

### Access the app

Open your configured domain in a browser.

---

## 📁 Project Structure

```text
.
├── Dockerfile
├── server.js
├── index.html
└── README.md
```

---

## ⚠️ Notes

- If you add new files, make sure your Dockerfile includes them.
- Default container port is 80 — change if needed.
- Prefer version tags (v1, v2, etc.) over only latest.

---

## 🔐 Security

- Never commit secrets or tokens.
- If a token was exposed, revoke it immediately and create a new one.

---

## 🧠 Workflow Summary

```bash
# Edit code
git add .
git commit -m "update"
git push

# Build + publish container
docker build -t ghcr.io/dofus-ai/starfield:vX .
docker push ghcr.io/dofus-ai/starfield:vX
```

---

Enjoy building 🚀
