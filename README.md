# DevOps Pipeline Practice Project

This repository demonstrates a **DevOps pipeline** implementation using a **Laravel application** with **PHP, Apache, and MySQL** services. It showcases a full deployment pipeline leveraging Docker, Docker Compose, Ansible, Terraform, and Jenkins, highlighting fundamental practices in automated infrastructure setup and continuous integration/deployment (CI/CD).

> **⚠ Disclaimer:** This project is for **practicing purposes only** and is **not intended for production**.

## Project Overview

The pipeline automates:

1. **Containerization** with Docker and Docker Compose.
2. **Automation** using Ansible playbooks.
3. **Infrastructure setup** using Terraform to provision Jenkins on an EC2 instance.
4. **Deployment automation** with Jenkins jobs.

---

## Project Components

1. **Dockerfile**: Defines the `php-apache` image for the Laravel application.
2. **docker-compose.yml**: Breaks down the app into microservices (`php-apache`, `mysql`, and `phpmyadmin`).
3. **Ansible Playbooks**: Automates Dockerfile builds, image pushes, and Docker Compose operations.
4. **Terraform**: Creates and manages Jenkins EC2 instance.
5. **Jenkins**: Executes pipeline jobs and automates the application's deployment.

---

## Pipeline Steps

### Step 1: Build Jenkins EC2 Instance
   ```sh
   cd terraform
   terraform init
   terraform apply -auto-approve
   ```

### Step 2: Connect to EC2 Instance
   ```sh
   ssh -i file.pem ec2-user@<Public IPv4 DNS>
   ```

### Step 3: Install Dependencies
   ```sh
   # Create and run the install script in EC2
   vim install.sh
   chmod +x install.sh
   ./install.sh
   ```

### Step 4: Access Jenkins
   ```plaintext
   http://<ec2-Public IPv4 DNS>:8080
   ```

### Step 5-13: Pipeline Execution
   - Set up Jenkins jobs for Docker Compose and Kubernetes-based deployments, access the application, and manage the EKS cluster.

---

## Creating a Jenkins Pipeline

1. Build infrastructure using Terraform.
2. SSH into the EC2 instance to install dependencies.
3. Access Jenkins and add Docker Hub/GitHub credentials.
4. Configure and run the pipeline.

---

## Suggested Repository Name

- `devops-pipeline-practice`
- `laravel-devops-practice`

---
