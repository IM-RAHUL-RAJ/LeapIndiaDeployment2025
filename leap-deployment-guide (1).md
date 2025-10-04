# Leap Cloud Deployment Guide 2025

## Prerequisites

### Login to JFrog Artifactory

```bash
docker login <artifactory_URL>
```

Enter your username and password when prompted.

---

## Application Components

This guide covers containerization for 4 applications:
- **Frontend** (Angular)
- **Midtier** (Node)
- **Backend** (Spring Boot)
- **FMTS** (Node)

---

## 1. Frontend - Angular

### Setup

Navigate to the frontend folder:

```bash
cd frontend
```

Create a Dockerfile and copy content from `<git_url>`

⚠️ **Important:** Update the ports according to your application configuration

### Build, Tag & Push

**Step 1:** Build the Docker image

```bash
docker build -t <frontend-projectname-corpid>:<image_version> .
```

**Step 2:** Tag the image for JFrog Artifactory

```bash
docker tag <frontend-projectname-corpid>:<image_version> <jfrog-url>/<fse-group-classroom>/<frontend-projectname-corpid>:<image_version>
```

**Step 3:** Push the image to JFrog Artifactory

```bash
docker push <jfrog-url>/<fse-group-classroom>/<frontend-projectname-corpid>:<image_version>
```

---

## 2. Midtier - Node

### Setup

Navigate to the midtier folder:

```bash
cd midtier
```

Create a Dockerfile and copy content from `<git_url>`

⚠️ **Important:** Update the ports according to your application configuration

### Build, Tag & Push

**Step 1:** Build the Docker image

```bash
docker build -t <midtier-projectname-corpid>:<image_version> .
```

**Step 2:** Tag the image for JFrog Artifactory

```bash
docker tag <midtier-projectname-corpid>:<image_version> <jfrog-url>/<fse-group-classroom>/<midtier-projectname-corpid>:<image_version>
```

**Step 3:** Push the image to JFrog Artifactory

```bash
docker push <jfrog-url>/<fse-group-classroom>/<midtier-projectname-corpid>:<image_version>
```

---

## 3. Backend - Spring Boot

### Setup

Navigate to the Spring Boot folder:

```bash
cd springboot
```

Create a Dockerfile and copy content from `<git_url>`

⚠️ **Important:** Update the ports according to your application configuration

### Build, Tag & Push

**Step 1:** Build the Docker image

```bash
docker build -t <backend-projectname-corpid>:<image_version> .
```

**Step 2:** Tag the image for JFrog Artifactory

```bash
docker tag <backend-projectname-corpid>:<image_version> <jfrog-url>/<fse-group-classroom>/<backend-projectname-corpid>:<image_version>
```

**Step 3:** Push the image to JFrog Artifactory

```bash
docker push <jfrog-url>/<fse-group-classroom>/<backend-projectname-corpid>:<image_version>
```

---

## 4. FMTS - Node

### Setup

Navigate to the FMTS folder:

```bash
cd fmts
```

Create a Dockerfile and copy content from `<git_url>`

⚠️ **Important:** Update the ports according to your application configuration

### Build, Tag & Push

**Step 1:** Build the Docker image

```bash
docker build -t <fmts-projectname-corpid>:<image_version> .
```

**Step 2:** Tag the image for JFrog Artifactory

```bash
docker tag <fmts-projectname-corpid>:<image_version> <jfrog-url>/<fse-group-classroom>/<fmts-projectname-corpid>:<image_version>
```

**Step 3:** Push the image to JFrog Artifactory

```bash
docker push <jfrog-url>/<fse-group-classroom>/<fmts-projectname-corpid>:<image_version>
```

---

## Example Usage

Here's a complete example for the frontend component:

```bash
# Build
docker build -t frontend-marshal-a900003:1.0 .

# Tag
docker tag frontend-marshal-a900003:1.0 rahulraj.jfrog.io/rahul-repo/frontend-marshal-a900003:1.0

# Push
docker push rahulraj.jfrog.io/rahul-repo/frontend-marshal-a900003:1.0
```

---

## Key Reminders

- Always navigate to the correct folder before building Docker images
- Ensure ports in Dockerfile match your application configuration
- Use consistent naming conventions across all components
- Replace placeholder values with your actual project details