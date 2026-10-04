# Jenkins CI/CD Pipeline Task

## Project Overview

This project demonstrates a simple CI/CD pipeline using Jenkins, GitHub, Node.js, and Docker.

Whenever a new code change is pushed to the GitHub repository, Jenkins automatically detects the change and runs the pipeline.

## Technologies Used

- GitHub
- Jenkins
- Node.js
- Express.js
- Docker
- Git

## Application

The application is a simple Node.js Express server.

Application URL:

http://localhost:3000

Expected output:

Hello! Jenkins CI/CD Pipeline is working 🚀

## CI/CD Pipeline

The Jenkins pipeline contains the following stages:

1. Build
   - Installs Node.js dependencies using npm install.

2. Test
   - Checks JavaScript syntax using node --check app.js.

3. Docker Build
   - Builds the Docker image jenkins-cicd-app:latest.

4. Deploy
   - Stops and removes the previous container.
   - Starts a new Docker container.
   - Maps port 3000 of the container to port 3000 on the host.

## Pipeline Flow

GitHub Commit
→ Jenkins
→ Build
→ Test
→ Docker Build
→ Deploy
→ Running Docker Container

## Automatic Trigger

Jenkins is configured with Poll SCM to periodically check the GitHub repository for new commits.

When a new commit is detected, Jenkins automatically starts the pipeline.

## How to Run Locally

Clone the repository:

git clone https://github.com/vigneshMatheshwaran/jenkins-cicd-task.git

Go to the project directory:

cd jenkins-cicd-task

Install dependencies:

npm install

Start the application:

node app.js

Open:

http://localhost:3000

## Run Using Docker

Build the Docker image:

docker build -t jenkins-cicd-app:latest .

Run the container:

docker run -d --name jenkins-cicd-container -p 3000:3000 jenkins-cicd-app:latest

## Jenkinsfile

The Jenkinsfile defines the complete CI/CD pipeline and automates:

- Application build
- Testing
- Docker image creation
- Application deployment

## Result

The Jenkins pipeline successfully builds, tests, creates a Docker image, and deploys the application automatically after a GitHub code change.

Pipeline Status:

SUCCESS
