# StarField

A simple containerized app that can be run with plain Docker from the command line and serves a mockup starship dashboard with a 3D map


---

## 🚀 Requirements

### Docker
Make sure Docker is installed:

https://docs.docker.com/get-docker/

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
