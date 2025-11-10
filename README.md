# Hello World - Vercel & Docker Deployment

A simple Hello World application ready for deployment on Vercel and Docker Hub.

[![Docker Hub](https://img.shields.io/badge/Docker%20Hub-Image-blue)](https://hub.docker.com/r/stoicpath/hello-world-vercel)

[![Vercel](https://img.shields.io/badge/Vercel-Deploy-black)](https://vercelhelloworld-tau.vercel.app/)

## 📋 Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Local Development](#local-development)
- [Docker Deployment](#docker-deployment)
  - [Step 1: Build Docker Image](#step-1-build-docker-image)
  - [Step 2: Run Docker Container Locally](#step-2-run-docker-container-locally)
  - [Step 3: Push to Docker Hub](#step-3-push-to-docker-hub)
- [Vercel Deployment](#vercel-deployment)
- [Screenshots](#screenshots)
- [Technologies Used](#technologies-used)
- [License](#license)

## 🔍 Overview

This is a lightweight Hello World application featuring:
- Simple and clean HTML structure
- Docker containerization with nginx
- Ready for Vercel deployment
- Fully documented code with English comments

## ✅ Prerequisites

Before you begin, ensure you have the following installed:

- [Git](https://git-scm.com/downloads) (v2.0+)
- [Docker Desktop](https://www.docker.com/products/docker-desktop) (v20.0+)
- [Node.js](https://nodejs.org/) (v14.0+ - optional for local dev)
- A [Docker Hub](https://hub.docker.com/) account
- A [Vercel](https://vercel.com/) account (optional)

## 📁 Project Structure

```
vercel_hello_world/
├── .dockerignore       # Files to exclude from Docker build
├── .git/               # Git version control directory
├── .gitignore          # Git ignore rules
├── Dockerfile          # Docker configuration for containerization
├── package.json        # Node.js project configuration
├── vercel.json         # Vercel deployment configuration
├── README.md           # Project documentation (this file)
├── frontend/           # Frontend application folder
│   └── index.html      # Main HTML page with detailed English comments
├── docs/               # Additional documentation folder
│   ├── package-json-explanation.md    # Explains package.json structure
│   └── vercel-json-explanation.md     # Explains vercel.json structure
└── screenshots/        # Screenshots folder for documentation
    └── README.md       # Instructions for screenshot placement
```

## 🐳 Docker Deployment

### Step 1: Build Docker Image

Open your terminal in the project directory and run:

```bash
# Build the Docker image
docker build -t hello-world-vercel .

# Verify the image was created
docker images | grep hello-world-vercel
```

**Expected output:**
```
hello-world-vercel   latest    abc123def456   X seconds ago   XX.XMB
```

### Step 2: Run Docker Container Locally

```bash
# Run the container
docker run -d -p 8080:80 --name hello-world-container hello-world-vercel

# Verify container is running
docker ps
```

**Expected output:**
```
CONTAINER ID   IMAGE                COMMAND                  CREATED         STATUS         PORTS                  NAMES
abc123def456   hello-world-vercel   "/docker-entrypoint.…"   X seconds ago   Up X seconds   0.0.0.0:8080->80/tcp   hello-world-container
```

**Test the application:**
Open your browser and navigate to `http://localhost:8080`

**To stop and remove the container:**
```bash
docker stop hello-world-container
docker rm hello-world-container
```

### Step 3: Push to Docker Hub

First, log in to Docker Hub:

```bash
# Login to Docker Hub
docker login

# Enter your Docker Hub username and password when prompted
```

Tag and push your image:

```bash
# Tag the image
docker tag hello-world-vercel stoicpath/hello-world-vercel:latest

# Push to Docker Hub
docker push stoicpath/hello-world-vercel:latest

# Optional: Push with version tag
docker tag hello-world-vercel stoicpath/hello-world-vercel:v1.0.0
docker push stoicpath/hello-world-vercel:v1.0.0
```

**Verify on Docker Hub:**
Visit https://hub.docker.com/r/stoicpath/hello-world-vercel

### Pull and Run from Docker Hub

Anyone can now pull and run your image:

```bash
# Pull the image
docker pull stoicpath/hello-world-vercel:latest

# Run the container
docker run -d -p 8080:80 stoicpath/hello-world-vercel:latest
```

## 🚀 Vercel Deployment

### Option 1: Using Vercel CLI

```bash
# Install Vercel CLI globally
npm install -g vercel

# Deploy to Vercel
vercel

# Follow the prompts to login and deploy
```

### Option 2: Using Git + Vercel Dashboard

1. Push your code to GitHub (see commands below)
2. Go to [vercel.com](https://vercel.com)
3. Click "New Project"
4. Import your GitHub repository
5. Click "Deploy"

### Option 3: Drag & Drop

1. Go to [vercel.com](https://vercel.com)
2. Login to your account
3. Drag and drop your project folder directly to the dashboard

## 📸 Screenshots

### Application Running Locally
![Local Development](screenshots/local-dev.png)
*Screenshot: Application running on localhost*

### Docker Build Process
![Docker Build](screenshots/docker-build.png)
*Screenshot: Docker image build process*

### Docker Container Running
![Docker Running](screenshots/docker-running.png)
*Screenshot: Container running successfully*

### Docker Hub Repository
![Docker Hub](screenshots/dockerhub-repo.png)
*Screenshot: Image published on Docker Hub*

### Vercel Deployment
![Vercel Deploy](screenshots/vercel-deploy.png)
*Screenshot: Application deployed on Vercel*

## 🛠️ Technologies Used

- **HTML5** - Markup structure with detailed comments
- **Docker** - Containerization
- **Nginx Alpine** - Web server (lightweight)
- **Vercel** - Serverless deployment platform
- **Node.js** - Development server (optional)

## 📝 Commands Reference

### Docker Commands
```bash
# Build image
docker build -t hello-world-vercel .

# Run container
docker run -d -p 8080:80 --name hello-world-container hello-world-vercel

# View running containers
docker ps

# View logs
docker logs hello-world-container

# Stop container
docker stop hello-world-container

# Remove container
docker rm hello-world-container

# Remove image
docker rmi hello-world-vercel

# Login to Docker Hub
docker login

# Tag image
docker tag hello-world-vercel stoicpath/hello-world-vercel:latest

# Push to Docker Hub
docker push stoicpath/hello-world-vercel:latest
```

### Git Commands
```bash
# Initialize repository
git init

# Add files
git add .

# Commit changes
git commit -m "Initial commit: Hello World project"

# Add remote repository
git remote add origin https://github.com/Stoic-path/vercel_hello_world.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## 🔗 Useful Links

- **Docker Hub Image**: https://hub.docker.com/r/stoicpath/hello-world-vercel
- **GitHub Repository**: https://github.com/Stoic-path/vercel_hello_world
- **Vercel Deployment**: `https://your-project.vercel.app` (update after deployment)

## 📄 License

MIT License - feel free to use this project for learning purposes.

## 👤 Author

Created as a demonstration project for distributed programming course.

**Repository**: [github.com/Stoic-path/vercel_hello_world](https://github.com/Stoic-path/vercel_hello_world)  
**Docker Image**: [hub.docker.com/r/stoicpath/hello-world-vercel](https://hub.docker.com/r/stoicpath/hello-world-vercel)

---

**Note:** This project includes detailed English comments in the HTML file and separate documentation files for JSON configurations in the `docs/` folder.
