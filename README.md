# irysan-tech-test

## 🧪 Test Description

Create a simple **"Hello World"** web application (for example, in Python or Node.js) and deploy it to a cloud infrastructure, such as an AWS account, using appropriate tools and best practices.

You are expected to demonstrate:
- Containerisation
- Pipelines
- A minimal orchestration setup of your choice

✅ **When deployed, the root URL should display `Hello World`.**

---

## 📋 Requirements

1. A Kubernetes cluster (**EKS preferred**)
2. GitHub Secrets configured:
   - `AWS_ACCESS_KEY_ID` – AWS credentials
   - `AWS_SECRET_ACCESS_KEY` – AWS credentials
   - `AWS_REGION` – e.g. `us-east-1`
   - `ECR_REPOSITORY` – e.g. `<aws_account_id>.dkr.ecr.<region>.amazonaws.com`
   - `KUBECONFIG_DATA` – your kubeconfig file in base64 format

---

## ✅ Solution Overview

### 🌐 Web Application: Build and Deploy

1. Create a simple `Dockerfile` with the Hello World app.
2. Create a GitHub Actions pipeline to:
   - Build and push the Docker image to Amazon ECR.
   - Deploy the new version to the Kubernetes cluster.
3. Deploy the application using **Helm** to manage:
   - The deployment
   - Service
   - Ingress

---

## 📁 Project Structure

```
hello-web-app/
├── .github/
│   └── workflows/
│       └── build-and-deploy.yml
├── Dockerfile
├── app.py
└── helm/
    ├── Chart.yaml
    ├── values.yaml
    └── templates/
        ├── _helpers.tpl
        ├── ingress.yaml
        ├── service.yaml
        └── deployment.yaml
```
## ⚠️ Disclaimer

This project is a draft implementation intended to demonstrate a possible approach to the given problem.
It has **not been fully tested in a production environment** and may require adjustments, validation, and security hardening before use in real-world scenarios.