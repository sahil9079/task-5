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

<img width="1920" height="1080" alt="Screenshot (456)" src="https://github.com/user-attachments/assets/d339db67-115f-4a81-abb3-195d4cff3d66" />



<img width="1920" height="1080" alt="Screenshot (459)" src="https://github.com/user-attachments/assets/c4477a45-d056-4eb5-958a-c1c1d9d8cacb" />


<img width="1920" height="1080" alt="Screenshot (460)" src="https://github.com/user-attachments/assets/51664ec5-a894-490a-96fd-1a6a27113fcd" />


<img width="1920" height="1080" alt="Screenshot (462)" src="https://github.com/user-attachments/assets/4d0a6b34-c683-4bd1-84df-cae2ca68980a" />

<img width="1920" height="1080" alt="Screenshot (465)" src="https://github.com/user-attachments/assets/0555f920-4e4d-4640-8c8c-9f61a75fd6ba" />

<img width="1920" height="1080" alt="Screenshot (463)" src="https://github.com/user-attachments/assets/8b282934-802d-4e73-8e67-9e8aabcf9965" />


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


Then reapply the deployment:

kubectl rollout restart deployment nginx-deployment



