# Project 5 — Build and Push a Docker Image Using Jenkins

## Project Objective

The objective of this project is to automate the Docker image build process using a Jenkins Pipeline.

I created a simple Node.js application, containerized it using Docker, and configured Jenkins to clone the source code from GitHub and build the Docker image automatically.

The completed image was also pushed to Docker Hub so that it can be downloaded and used from another machine.

## Project Workflow

```text
Developer
    ↓
GitHub Repository
    ↓
Jenkins Pipeline
    ↓
Checkout Source Code
    ↓
Build Docker Image
    ↓
Verify Docker Image
    ↓
Push Image to Docker Hub
```

## Tools Used
```text
Jenkins
Docker
Git
GitHub
Docker Hub
Node.js
Ubuntu on WSL
```

## Project Files
```test
project5-builddockerimage/
├── app.js
├── package.json
├── Dockerfile
├── Jenkinsfile
├── README.md
├── notes.md
└── screenshots/
```

## Application

The application is a simple Node.js web server that runs on port 3000.

When the application is opened, it displays:
```bash
Hello from Jenkins Docker Pipeline!
```

## Dockerfile

The Dockerfile performs the following tasks:

- Uses the Node.js Alpine image.
- Creates /app as the working directory.
- Copies the application files.
- Exposes port 3000.
- Starts the application using npm start.

## Jenkins Pipeline

The Jenkins Pipeline reads the source code from GitHub and performs the following stages:
### Build Docker Image
```bash
docker build -t jenkins-project5-demo .
```
This command builds the Docker image using the Dockerfile.
### Verify Docker Image
```bash
docker images | grep jenkins-project5-demo
```
This confirms that the image was created successfully.
### Docker Hub Push
The local image was tagged using my Docker Hub username:
```bash
docker tag \
  jenkins-project5-demo:latest \
  ashasrivallibanka/jenkins-project5-demo:latest
```
The image was then pushed using:
```bash
docker push \
  ashasrivallibanka/jenkins-project5-demo:latest
```
### Run the Application
The image can be downloaded from Docker Hub using:
```bash
docker pull \
  ashasrivallibanka/jenkins-project5-demo:latest
```
Run the container:
```bash
docker run -d \
  --name jenkins-project5-test \
  -p 3000:3000 \
  ashasrivallibanka/jenkins-project5-demo:latest
```
Test the application:
```bash
curl http://localhost:3000
```
Expected output:
```bash
Hello from Jenkins Docker Pipeline!
```

## Outcome

The Jenkins Pipeline completed successfully and built the Docker image automatically.

The image was verified locally and pushed to Docker Hub for future use and deployment.
