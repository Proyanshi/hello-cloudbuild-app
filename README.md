# 🚀 GitOps CI/CD Pipeline with Google Cloud Build & Kubernetes

![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)

---

## 📌 About This Project

This project implements a **GitOps-style CI/CD pipeline** on Google Cloud that automatically builds, tests, and deploys a containerised Python web application to **Google Kubernetes Engine (GKE)** using **Cloud Build**.

Completed as part of the **Google Cloud Arcade program** — this hands-on project demonstrates real-world DevOps practices including automated testing, container image management, and GitOps-style deployment workflows.

---

## ⚙️ How It Works

When code is pushed to this repository, the following pipeline triggers automatically:

```
Code Push (GitHub)
       ↓
Cloud Build — runs automated tests
       ↓
Docker image built & pushed to Artifact Registry
       ↓
Kubernetes manifest updated with new image tag
       ↓
Deployed to GKE (candidate branch)
       ↓
On success → promoted to production branch ✅
```

This means:
- The **candidate branch** = history of all deployment attempts
- The **production branch** = history of only successful deployments
- Any failed deployment can be **rolled back** by re-running a previous Cloud Build job

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python + Flask** | Web application |
| **Docker** | Containerisation |
| **Google Cloud Build** | CI/CD pipeline automation |
| **Google Artifact Registry** | Container image storage |
| **Google Kubernetes Engine (GKE)** | Container orchestration & deployment |
| **Kubernetes Manifests** | Declarative deployment configuration |
| **GitOps** | Git as single source of truth for deployments |

---

## 📁 Repository Structure

```
hello-cloudbuild-app/
├── app.py                      # Flask web application
├── test_app.py                 # Automated tests
├── Dockerfile                  # Container image definition
├── cloudbuild.yaml             # CI pipeline (build + test)
├── cloudbuild-delivery.yaml    # CD pipeline (deploy to GKE)
├── cloudbuild-trigger-cd.yaml  # Trigger configuration
├── kubernetes.yaml.tpl         # Kubernetes deployment manifest template
└── known_hosts.github          # GitHub SSH configuration
```

---

## 💡 What I Learned

- How to set up a **fully automated CI/CD pipeline** from code commit to production
- How **GitOps** uses Git branches to track deployment history
- How to **containerise** a Python app with Docker
- How **Cloud Build triggers** work with GitHub repositories
- How to deploy and manage apps on **Google Kubernetes Engine**
- How to implement **automated rollbacks** using Cloud Build job history

---
<p align="center"><em>Built with ☁️ on Google Cloud | Part of Google Cloud Arcade — Diamond League</em></p>
