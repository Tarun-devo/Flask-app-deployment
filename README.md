# CI/CD Pipeline for Flask App with Kubernetes

This project demonstrates a complete CI/CD pipeline using GitHub Actions to build, test, Dockerize, and deploy a Flask web application to a Kubernetes cluster.

## 🚀 Tech Stack
- Flask (Python web framework)
- Docker
- Kubernetes (Minikube or cloud)
- GitHub Actions
- DockerHub (as container registry)

## 🛠️ Features
- Auto-build and test on push to `main`
- Docker image creation and push
- Kubernetes deployment with `kubectl`

## 📁 Project Structure
```
ci-cd-flask-k8s/
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
├── .github/workflows/
│   └── main.yaml
└── README.md
```

## ⚙️ Prerequisites
- DockerHub account
- Kubernetes cluster access (e.g., Minikube)
- GitHub repo with secrets set:
  - `DOCKER_USERNAME`
  - `DOCKER_PASSWORD`
  - `KUBECONFIG`

## 🔄 CI/CD Workflow
1. Developer pushes code to GitHub
2. GitHub Actions pipeline starts:
   - Install dependencies
   - Run tests
   - Build Docker image
   - Push image to DockerHub
   - Deploy to Kubernetes using `kubectl`

## 🖼️ Architecture Diagram
```
[GitHub] → [GitHub Actions] → [DockerHub]
                                  ↓
                            [Kubernetes Cluster]
```

## 🏁 How to Run Locally
```bash
cd app
pip install -r requirements.txt
python app.py
```

## 🐳 Build & Run with Docker
```bash
docker build -t flask-app:latest ./app
docker run -p 5000:5000 flask-app:latest
```

## 📦 Deploy to K8s
```bash
kubectl apply -f k8s/
kubectl get svc flask-service  # Access via NodePort
```

---

Happy DevOps-ing! 🎉
