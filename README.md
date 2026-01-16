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

**Screenshots of my efforts and results including some descriptions:**



Firstly I logged into WSL and created the needed files to push into the GitHub repo which includes python code for the app and requirements.txt file:

<img width="1069" height="445" alt="Screenshot 2026-01-15 202453" src="https://github.com/user-attachments/assets/d55e842b-fea5-4fd6-852d-10ba27ef2a8f" /><br>
<br>
<br>

I installed the Python packages and then decided to test the app by running it:

<img width="1119" height="406" alt="Screenshot 2026-01-15 202653" src="https://github.com/user-attachments/assets/b67c2da3-917c-4617-99b6-223aca41c2b1" />
<img width="495" height="222" alt="Screenshot 2026-01-15 202820" src="https://github.com/user-attachments/assets/4ae01a91-a77a-4ce4-b53c-763919f2dc03" />

<br>
<br>
<br>
<br>

I created a Dockerfile, ensured I have installed Docker for Desktop onto my machine and enabled WSL integration, and then sorted out permissions issue so I could rub a Docker build:

<img width="700" height="319" alt="Screenshot 2026-01-16 144616" src="https://github.com/user-attachments/assets/5a8b4a47-03d4-47d7-aecb-de10a2e2b3f6" />
<br>
<br>
<img width="1140" height="379" alt="Screenshot 2026-01-16 145646" src="https://github.com/user-attachments/assets/183eb036-d64d-4b7c-9a58-41d1ec019464" />
<br>
<br>
<img width="1120" height="528" alt="Screenshot 2026-01-16 150128" src="https://github.com/user-attachments/assets/51dd32c0-c9c3-4f5d-92d7-0fb8195003ba" /><br>
<br>
<br>






