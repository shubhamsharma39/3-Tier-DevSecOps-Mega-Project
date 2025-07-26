# 3-Tier DevSecOps Project

This repository contains a simple Node.js API and a React client used for a user management demo. Follow the steps below to get the project running locally.

## Setup

1. Install Node.js (version 18 or later is recommended).
2. Install dependencies for both the API and client:

   ```bash
   cd api && npm install
   cd ../client && npm install
   ```

3. Start the API server:

   ```bash
   cd api
   npm start
   ```

4. In a separate terminal, start the React client:

   ```bash
   cd client
   npm start
   ```

5. Open `http://localhost:3000` in your browser to use the application.

6. Folder Structure
.
├── api/ # Backend API (Node.js + Express)
├── client/ # React Frontend
├── Monitoring/ # Prometheus & Grafana config
├── Jenkinsfile_CICD # Jenkins pipeline definition
├── docker-compose.yaml # For local development
├── eks-steps.md # Guide to deploy on AWS EKS
├── Setup MySQL in LINUX.docx
└── README.md

7. Docker Setup (Optional)
    If you prefer running everything via Docker:
    docker-compose up --build
    This will spin up:

    MySQL DB

    Node.js API

    React Frontend

    Make sure to configure .env files properly for API and DB access.

8. CI/CD Pipeline with Jenkins
   Jenkins is used for automating build, test, and deployment.

   Steps:

   Jenkinsfile defines stages: Install, Lint/Test, Build, Dockerize, Deploy

   Use multibranch pipeline for GitHub integration

   Trigger pipeline on every push

9. Deploying to EKS (Kubernetes)
   Follow the steps in eks-steps.md to:

   Create EKS cluster using eksctl

   Deploy app manifests (Deployment, Service, Ingress)

   Use cert-manager for SSL

   Monitor with Prometheus + Grafana

10. Security Highlights
    JWT-based Authentication & Authorization

    Role-based Access Middleware

    Secrets managed using .env and optionally Kubernetes Secrets

11. Placeholder for tools like:

     Trivy (Container vulnerability scanner)

     SonarQube or ESLint for code quality

     Snyk integration for dependencies

12. Monitoring & Alerting
     Located in Monitoring/ folder:

     values.yaml for Prometheus/Grafana Helm config

     View resource usage, logs, alerts in Grafana dashboards

     Export metrics from Node.js via /metrics endpoint (if configured)


The client now displays an animated banner welcoming you to **DevOps Shack**.
