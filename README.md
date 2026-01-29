# 🚀 Python CI/CD Pipeline with GitHub Actions, Docker & AWS

This project demonstrates an **end-to-end DevOps workflow** for deploying a Python application on **AWS EC2** using **GitHub Actions, Docker, Docker Compose, SonarQube, and SMTP notifications**.

The setup follows **real-world DevOps practices** including Infrastructure as Code, CI/CD automation, code quality checks, containerization, and multi-service orchestration.

---

## 📌 Project Overview

The application is a **Flask-based Python service** deployed on an AWS EC2 instance.  
A **GitHub Actions–based CI/CD pipeline** is used to automate build, quality checks, and deployment.

The deployment includes:
- A Python Flask application
- A PostgreSQL database
- A Dockerized SMTP server (MailHog)

All services run on the **same EC2 instance** using **Docker Compose**.

---

## 🏗️ Architecture

```

GitHub
└── GitHub Actions (CI/CD)
│
▼
AWS EC2
├── SonarQube (Code Quality)
└── Docker
├── Flask Python App
├── PostgreSQL Database
└── MailHog (SMTP Server)

```

---

## 🛠️ Tools & Technologies Used

- **AWS EC2** – Cloud compute
- **Terraform** – Infrastructure as Code (IaC)
- **GitHub** – Source code management
- **GitHub Actions** – CI/CD automation
- **Docker** – Containerization
- **Docker Compose** – Multi-container orchestration
- **SonarQube** – Code quality & security analysis
- **Python (Flask)** – Application framework
- **PostgreSQL** – Database
- **MailHog** – SMTP server for email testing

---

## 📂 Repository Structure

```

ci-cd/
│── app/
│   └── app.py
│── Dockerfile
│── docker-compose.yml
│── requirements.txt
│── .github/
│   └── workflows/
│       └── ci-cd.yml
│── terraform/
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
└── README.md

```

---

## 🔄 CI/CD Workflow (GitHub Actions)

1. Code is pushed to the GitHub repository
2. GitHub Actions workflow is triggered
3. Application dependencies are installed
4. Code quality analysis is performed using SonarQube
5. Docker image is built
6. Application is deployed to AWS EC2
7. Email notifications are sent on pipeline success or failure using SMTP

---

## 📦 Containerized Services

### 1️⃣ Flask Application
- Runs on port `5000`
- Connects to PostgreSQL
- Sends emails via SMTP (MailHog)

### 2️⃣ PostgreSQL Database
- Runs in a Docker container
- Uses Docker volumes for persistent storage

### 3️⃣ MailHog (SMTP Server)
- SMTP port: `1025`
- Web UI: `8025`
- Used to capture and verify application emails

---

## ✅ Verification & Results

### Application Access
```

http://3.238.32.56:5000

```

Expected response:
```

CI/CD Pipeline Working! DB connected & Email sent.

```

---

### Email Verification
```

http://3.238.32.56:8025

````

Emails sent by the application are visible in the MailHog UI.

---

### Container Status
```bash
docker ps
````

All containers:

* python_app
* postgres_db
* mailhog

should be in **running** state.

---

## 🧠 Key Learnings

* Infrastructure provisioning using Terraform
* CI/CD automation using GitHub Actions
* Code quality enforcement with SonarQube
* Docker-based application containerization
* Multi-container orchestration using Docker Compose
* SMTP integration and email verification
* Debugging container restart loops and dependency issues

---

## 🏁 Project Status

**Status:** ✅ Completed
**Outcome:** Successfully implemented a production-style DevOps workflow using GitHub Actions, Docker, and AWS.

---

## 📌 Future Improvements

* Secure secrets using GitHub Secrets and `.env` files
* Add database migrations
* Implement health checks
* Deploy using a reverse proxy (Nginx)

```
