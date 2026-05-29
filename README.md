# AI-Powered Self-Healing CI/CD Pipeline

An intelligent DevOps and MLOps demonstration project that combines **CI/CD automation**, **machine learning-based failure prediction**, and **self-healing deployment strategies** inside a modern e-commerce environment.

The project simulates how large-scale platforms can automatically detect unstable deployments, monitor live system metrics, make AI-driven deployment decisions, and trigger rollback actions without manual intervention.

---

# Project Overview

This project includes:

* **AURUM React Storefront** with modern UI and Three.js background
* **Node.js Backend API** for metrics and service communication
* **FastAPI ML Service** for deployment health prediction
* **Docker Compose Infrastructure**
* **Jenkins CI/CD Pipeline**
* **Traffic Simulation Engine**
* **Self-Healing Monitoring Scripts**
* Optional **OMNeT++ integration sources**

The system continuously monitors application metrics such as:

* Error rate
* Response time
* Service availability

The ML model predicts whether the deployment state is:

* `SAFE`
* `FAIL`

If failure conditions are detected, the pipeline can automatically initiate rollback or recovery actions.

---

# System Architecture

```text
User Traffic
      ↓
React Frontend (AURUM)
      ↓
Node.js Backend API
      ↓
Metrics Collection
      ↓
FastAPI ML Classifier
      ↓
Prediction Engine
      ↓
SAFE / FAIL Decision
      ↓
Jenkins Self-Healing Pipeline
      ↓
Rollback / Redeploy / Recovery
```

---

# Tech Stack

## Frontend

* React.js
* Vite
* Three.js

## Backend

* Node.js
* Express.js

## Machine Learning Service

* FastAPI
* Scikit-learn
* Pandas
* NumPy

## DevOps & Infrastructure

* Docker
* Docker Compose
* Jenkins

## Simulation & Monitoring

* Python
* Traffic simulation scripts

---

# Features

* AI-powered deployment validation
* Automated rollback mechanism
* Real-time deployment monitoring
* CI/CD automation using Jenkins
* ML-based deployment risk prediction
* Dockerized multi-service architecture
* Traffic simulation for realistic testing
* Chaos engineering scripts for resilience testing

---

# Folder Structure

```text
ai-driven-self-healing-cicd-pipeline/
│
├── frontend/              # React storefront
├── backend/               # Node.js API
├── ml-service/            # FastAPI ML classifier
├── simulation/            # Traffic simulation scripts
├── notebooks/             # Jupyter notebooks
├── scripts/               # Monitoring & chaos scripts
├── docker-compose.yml
├── Jenkinsfile
└── README.md
```

---

# Prerequisites

Before running the project, install:

* Node.js 18+
* Python 3.11+
* Docker Desktop (optional)
* Jenkins (optional for CI/CD automation)

---

# Quick Start (Local Setup)

## 1. Generate Traffic Dataset

```powershell
cd simulation
python generate_traffic_csv.py
```

Copy generated CSV into ML service data folder if required:

```powershell
Copy-Item -Force data\traffic_simulation.csv ..\ml-service\data\
```

---

## 2. Train the ML Model

```powershell
cd ml-service
pip install -r requirements.txt
python train_from_csv.py
```

This generates:

```text
model.pkl
```

which is used for deployment prediction.

---

## 3. Start the ML Service

```powershell
python -m uvicorn main:app --host 0.0.0.0 --port 8000
```

The ML API exposes prediction endpoints for deployment health evaluation.

---

## 4. Start Backend API

```powershell
cd backend
npm install
npm start
```

The backend handles:

* metrics aggregation
* monitoring endpoints
* ML service communication

---

## 5. Start Frontend

```powershell
cd frontend
npm install
npm run dev
```

Launch the AURUM storefront using the generated frontend URL.

---

# Docker Compose Setup

From the repository root:

```powershell
docker compose up --build
```

This starts:

* Frontend service
* Backend API
* ML prediction service

---

# API Endpoints

| Endpoint                    | Description                 |
| --------------------------- | --------------------------- |
| `GET /health`               | Backend health check        |
| `GET /metrics/summary`      | Current rolling metrics     |
| `POST /metrics/ml-evaluate` | Sends metrics to ML service |
| `POST /predict`             | Predict deployment status   |

---

# Monitoring & Chaos Testing

## Monitor Script

```powershell
node scripts/monitor.mjs
```

The script:

* samples metrics
* calls the ML model
* exits with failure code if deployment risk is detected

---

# Jupyter Notebook

Open:

```text
notebooks/train_deployment_model.ipynb
```

The notebook includes:

* classifier comparison
* dataset visualization
* model evaluation
* deployment prediction experiments

---

# Jenkins CI/CD Pipeline

The included `Jenkinsfile` demonstrates a self-healing CI/CD workflow:

```text
Build
   ↓
Test
   ↓
Deploy
   ↓
Monitor
   ↓
ML Decision
   ↓
Rollback / Continue
```

Pipeline capabilities include:

* automated builds
* deployment validation
* ML-driven deployment decisions
* automatic rollback handling

---

# Running Tests

```powershell
cd backend
npm test
```

---

# Future Improvements

* Kubernetes deployment support
* Prometheus + Grafana monitoring
* Cloud deployment support (AWS/GCP/Azure)
* Distributed multi-node orchestration
* Real-time alerting system

---

# Learning Outcomes

This project demonstrates practical concepts from:

* DevOps
* MLOps
* CI/CD Automation
* Machine Learning Operations
* System Reliability Engineering
* Chaos Engineering
* AI-driven Infrastructure Monitoring

---

# Author

Developed as an advanced AI + DevOps demonstration project focused on intelligent deployment automation and self-healing infrastructure systems.
