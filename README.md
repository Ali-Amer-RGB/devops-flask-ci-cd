# devops-flask-ci-cd
End-to-end CI/CD pipeline for a Dockerized Flask application using GitHub Actions and AWS EC2.

# Overview
This project demonstrates a simple production-style DevOps workflow:
- Build and package a Flask app into a Docker image
- Automatically build and push the image to Docker Hub using GitHub Actions (CI)
- Deploy the containerized app to an AWS EC2 instance (CD)

## Architecture
**Flow:**
1. Code is pushed to GitHub (`main` branch)
2. GitHub Actions builds a Docker image from the Dockerfile
3. The image is pushed to Docker Hub
4. AWS EC2 pulls the latest image and runs the container
5. The Flask app is accessible via the EC2 public IP

## Tech Stack
- Python (Flask)
- Docker + Docker Hub
- GitHub Actions (CI/CD)
- AWS EC2 (Ubuntu)
