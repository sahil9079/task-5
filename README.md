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
<img width="1920" height="1080" alt="Screenshot (456)" src="https://github.com/user-attachments/assets/4bfa5d53-69e7-4c70-a572-7f47312ef209" />

🧠 Problems Faced 
❌ Problem 1: ImagePullBackOff

Error Message:

Failed to pull image "nginx:latest": dial tcp: lookup docker-images-prod... no such host


Cause:
Minikube’s internal VM couldn’t reach Docker Hub due to DNS resolution issues.

Solution:

docker pull nginx:latest
minikube image load nginx:latest
<img width="1920" height="1080" alt="Screenshot (460)" src="https://github.com/user-attachments/assets/8e0f7f11-d07d-4aef-b954-18103e50af12" />


Then reapply the deployment:

kubectl rollout restart deployment nginx-deployment
<img width="1920" height="1080" alt="Screenshot (461)" src="https://github.com/user-attachments/assets/ab99b5d0-be0e-4e1d-bf68-d168075fec79" />

<img width="1920" height="1080" alt="Screenshot (459)" src="https://github.com/user-attachments/assets/1fdb0bc4-0be7-4ce1-85a2-5ba36fa2ae01" />

<img width="1920" height="1080" alt="Screenshot (465)" src="https://github.com/user-attachments/assets/837b7300-2fac-4421-b06d-03a3d295638d" />

<img width="1920" height="1080" alt="Screenshot (463)" src="https://github.com/user-attachments/assets/331d60ef-b884-4429-882d-49a9861b1e6f" />

