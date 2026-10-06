# AWS Docker CI/CD Web Application

## Project Overview

This project demonstrates a containerized web application deployed on AWS EC2 using Docker, Amazon ECR, GitHub Actions, IAM OIDC, and AWS Systems Manager.

## Architecture

GitHub
→ GitHub Actions
→ Docker Build
→ Amazon ECR
→ AWS Systems Manager
→ Amazon EC2
→ Docker Container
→ Nginx Web Application

## Technologies Used

- AWS EC2
- Ubuntu Linux
- Docker
- Dockerfile
- Amazon ECR
- GitHub Actions
- AWS IAM
- GitHub OIDC
- AWS Systems Manager
- Nginx
- HTML

## Implementation

1. Created a custom HTML web application.
2. Created a Dockerfile using Nginx.
3. Built a custom Docker image.
4. Ran the application inside an EC2 Docker container.
5. Created a private Amazon ECR repository.
6. Pushed the Docker image to ECR.
7. Configured GitHub Actions for automated Docker builds.
8. Configured GitHub OIDC authentication with AWS IAM.
9. Automated image deployment to EC2 using AWS Systems Manager.
10. Verified the deployed application through a web browser.

## CI/CD Workflow

A push to the `main` branch triggers GitHub Actions.

The workflow:

- Checks out the source code.
- Builds the Docker image.
- Authenticates to AWS using OIDC.
- Pushes the image to Amazon ECR.
- Uses AWS Systems Manager to deploy the image to EC2.
- Restarts the Docker container with the new image.

## Docker

The application is packaged using:

```dockerfile
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
