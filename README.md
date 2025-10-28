# 🧩 TASK 5 — Build a Kubernetes Cluster Locally with Minikube

## 🎯 Objective
Deploy and manage an application on a **Kubernetes cluster** running locally using **Minikube** with **Docker** as the driver.

---

## 🧰 Tools Used
- **Minikube**
- **kubectl**
- **Docker Desktop (Windows 11)**
- **PowerShell / Command Prompt**
- **YAML files** (`deployment.yaml`, `service.yaml`)

---

## ⚙️ Setup Workflow

### 1️⃣ Verify Tools Installation
```bash
kubectl version --client
docker version
minikube version

Start Minikube Cluster
minikube start --driver=docker

Apply the deployment
kubectl apply -f deployment.yaml

Apply the service:
kubectl apply -f service.yaml

🧠 Problems Faced 
❌ Problem 1: ImagePullBackOff

Error Message:

Failed to pull image "nginx:latest": dial tcp: lookup docker-images-prod... no such host


Cause:
Minikube’s internal VM couldn’t reach Docker Hub due to DNS resolution issues.

Solution:

docker pull nginx:latest
minikube image load nginx:latest


Then reapply the deployment:

kubectl rollout restart deployment nginx-deployment
