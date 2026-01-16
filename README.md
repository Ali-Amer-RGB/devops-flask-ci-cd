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


**Firstly I logged into WSL and created the needed files to push into the GitHub repo which includes python code for the app and requirements.txt file:**

<img width="1069" height="445" alt="Screenshot 2026-01-15 202453" src="https://github.com/user-attachments/assets/d55e842b-fea5-4fd6-852d-10ba27ef2a8f" /><br>
<br>
<br>
<br>
<br>
<br>
<br>

**I installed the Python packages and then decided to test the app by running it:**

<img width="1119" height="406" alt="Screenshot 2026-01-15 202653" src="https://github.com/user-attachments/assets/b67c2da3-917c-4617-99b6-223aca41c2b1" />
<br>
<br>
<img width="495" height="222" alt="Screenshot 2026-01-15 202820" src="https://github.com/user-attachments/assets/4ae01a91-a77a-4ce4-b53c-763919f2dc03" />
<br>
<br>
<br>
<br>
<br>
<br>


**I created a Dockerfile, ensured I have installed Docker for Desktop onto my machine and enabled WSL integration, and then sorted out permissions issue so I could rub a Docker build:**

<img width="700" height="319" alt="Screenshot 2026-01-16 144616" src="https://github.com/user-attachments/assets/5a8b4a47-03d4-47d7-aecb-de10a2e2b3f6" />
<br>
<br>
<img width="1140" height="379" alt="Screenshot 2026-01-16 145646" src="https://github.com/user-attachments/assets/183eb036-d64d-4b7c-9a58-41d1ec019464" />
<br>
<br>
<img width="1120" height="528" alt="Screenshot 2026-01-16 150128" src="https://github.com/user-attachments/assets/51dd32c0-c9c3-4f5d-92d7-0fb8195003ba" /><br>
<br>
<br>
<br>
<br>
<br>
<br>

**I cleaned up any existing containers and initiated the container. And then I pushed the image to my DockerHub:**

<img width="1046" height="319" alt="Screenshot 2026-01-16 150157" src="https://github.com/user-attachments/assets/821125df-b14a-4370-b26e-6e6957a00ddd" />
<br>
<br>
<img width="407" height="199" alt="Screenshot 2026-01-16 150226" src="https://github.com/user-attachments/assets/a695c1d2-8399-4a98-81ea-67fe64fb491e" />
<br>
<br>
<img width="1057" height="253" alt="Screenshot 2026-01-16 150733" src="https://github.com/user-attachments/assets/16f6f958-9a32-4e6d-b503-acc96f003602" />
<br>
<br>
<br>
<br>
<br>
<br>

**I pushed the files to my Github Repo and made sure I have set the correct configurations for a successful connection:**

<img width="911" height="288" alt="Screenshot 2026-01-16 151536" src="https://github.com/user-attachments/assets/02bf5623-2d96-4886-b46a-302fad260a9d" />
<br>
<br>
<br>
<br>
<br>
<br>

**I generated a SSH key, started the SSH agent and then configured Github authentication for sercure, passwordless, repository access:**

<img width="981" height="564" alt="Screenshot 2026-01-16 152133" src="https://github.com/user-attachments/assets/cb3e5852-c6b3-497c-85e0-02cc2985572c" />
<br>
<br>
<img width="1016" height="619" alt="Screenshot 2026-01-16 152230" src="https://github.com/user-attachments/assets/7b554d38-1221-4292-b3c5-7cec9806c83e" />
<br>
<br>
<br>
<br>
<br>
<br>


**I resolved a Git push rejection by rebasing local changes, then implemented a GitHub Actions CI pipeline to automatically build and push a Docker image to Docker Hub on every push to main branch:**

<img width="840" height="563" alt="Screenshot 2026-01-16 152632" src="https://github.com/user-attachments/assets/f0d6b39d-4c02-4d6a-8ef7-dd306fdc038a" />
<br>
<br>
<img width="889" height="660" alt="Screenshot 2026-01-16 152850" src="https://github.com/user-attachments/assets/90588a2b-4f0a-43e7-acab-17ce540ed3bb" />
<br>
<br>
<br>
<br>
<br>
<br>


**I committed and pushed a GitHub Actions workflow, generated a Docker Hub access token, and configured encrypted GitHub Secrets to enable automated Docker image builds and pushes:**

<img width="1038" height="291" alt="Screenshot 2026-01-16 153758" src="https://github.com/user-attachments/assets/9d07a98e-096f-4fb1-a46b-52e3be50b1e5" />
<br>
<br>
<img width="1037" height="761" alt="Screenshot 2026-01-16 154424" src="https://github.com/user-attachments/assets/0d0927b5-6f20-4baa-889e-7419ee51fcb3" />
<br>
<br>
<img width="856" height="692" alt="Screenshot 2026-01-16 154548" src="https://github.com/user-attachments/assets/995ebe53-0aa5-4c6c-bbb3-f122fdd29cf4" />
<br>
<br>
<br>
<br>
<br>
<br>

**I triggered and verified a successful GitHub Actions CI run using an empty commit, confirming automated Docker image build and push functionality:**

<img width="790" height="187" alt="Screenshot 2026-01-16 155247" src="https://github.com/user-attachments/assets/59f1bb90-d9b6-417d-8e23-e2b6c6d676ab" />
<br>
<br>
<img width="2487" height="1275" alt="Screenshot 2026-01-16 155336" src="https://github.com/user-attachments/assets/1974ac77-92ba-4dc4-ad4d-cc820c3405b0" />
<br>
<br>
<br>
<br>
<br>
<br>

**I provisioned an AWS EC2 instance and securely connected via SSH using a key pair, preparing the server for application deployment:**

<img width="2244" height="34" alt="Screenshot 2026-01-16 160049" src="https://github.com/user-attachments/assets/011a7846-5338-483c-9287-7ee8f0f81cc7" />
<br>
<br>
<img width="911" height="919" alt="Screenshot 2026-01-16 160344" src="https://github.com/user-attachments/assets/689b2a4b-a51f-440e-a3e4-ff68d05259a9" />
<br>
<br>
<br>
<br>
<br>
<br>

**I deployed the Dockerized Flask application to an AWS EC2 instance by pulling the CI-built image from Docker Hub and running it as a production container:**

<img width="771" height="397" alt="Screenshot 2026-01-16 160512" src="https://github.com/user-attachments/assets/e01b3af8-05e3-4531-b5fb-26315079784b" />
<br>
<br>
<img width="1022" height="63" alt="Screenshot 2026-01-16 160531" src="https://github.com/user-attachments/assets/0d3366b1-06f1-42a3-847d-d22f15090ac2" />
<br>
<br>
<img width="501" height="171" alt="Screenshot 2026-01-16 160627" src="https://github.com/user-attachments/assets/b4404d39-738b-4fd4-9a0f-de5c773e58fb" />
<br>
<br>
<br>
<br>
<br>
<br>

**I added Nginx as a reverse proxy in front of the Dockerized Flask application and implemented a deployment script to automate container updates on the EC2 instance:**

<img width="1112" height="595" alt="Screenshot 2026-01-16 161245" src="https://github.com/user-attachments/assets/0b9142dd-7bde-4c67-b85b-50a6597d3ffd" />
<br>
<br>
<img width="1104" height="295" alt="Screenshot 2026-01-16 161309" src="https://github.com/user-attachments/assets/11d04904-a7b8-40d2-8b61-3bdae073e72c" />
<br>
<br>
<br>
<br>
<br>
<br>

**I generated a dedicated SSH key for GitHub Actions and configured encrypted repository secrets to allow secure, automated deployments to an EC2 instance:**

<img width="1159" height="422" alt="Screenshot 2026-01-16 161427" src="https://github.com/user-attachments/assets/7b040e3d-fda4-43d7-8717-4a0ca1fc8f93" />
<br>
<br>
<img width="836" height="435" alt="Screenshot 2026-01-16 163853" src="https://github.com/user-attachments/assets/dfcd5aa7-c22c-4b68-91c5-24ea1698f4b9" />
<br>
<br>
<br>
<br>
<br>
<br>

**I implemented a full CI/CD pipeline using GitHub Actions to automatically build, push, and deploy a Dockerized Flask application to AWS EC2 via SSH and Nginx:**

<img width="1085" height="940" alt="Screenshot 2026-01-16 164018" src="https://github.com/user-attachments/assets/df79f9ab-6493-4001-b9a0-07e7eb864acd" />
<br>
<br>
<img width="968" height="348" alt="Screenshot 2026-01-16 164320" src="https://github.com/user-attachments/assets/d6231085-7c55-4ae4-9a0b-c13581155ad0" />
<br>
<br>
<img width="2487" height="1165" alt="Screenshot 2026-01-16 164802" src="https://github.com/user-attachments/assets/4fb145b4-6037-4ec1-84ed-db59d8bc77a5" />
<br>
<br>
<img width="517" height="268" alt="Screenshot 2026-01-16 164850" src="https://github.com/user-attachments/assets/fbef5c57-0a32-4a85-afd5-c43844fb3bc6" />
<br>
<br>



















