# 📜 Quote API

A simple FastAPI-powered microservice that returns a random motivational quote. Designed for local development with Docker and deployed on Kubernetes using Minikube.

---

## 🚀 Features

- Built with **FastAPI**.
- Containerized with **Docker**.
- Deployed on **Kubernetes** via **Minikube**.
- Exposes a single endpoint: `/quote`.

---

## 📁 Project Structure

```
quote-api/
├── app/
│   ├── main.py          # FastAPI entry point
│   └── quotes.py        # List and logic for quotes
├── requirements.txt     # Python dependencies
├── Dockerfile           # Container spec
├── k8s/
│   ├── deployment.yaml  # Kubernetes Deployment
│   └── service.yaml     # Kubernetes Service
```

---

## 🐳 Run Locally with Docker

```bash
docker build -t quote-api:latest .
docker run -p 8000:8000 quote-api:latest
```

Access the API at: [http://localhost:8000/quote](http://localhost:8000/quote)

---

## ☘️ Deploy on Minikube

### 1. Start Minikube
```bash
minikube start
```

### 2. Point Docker CLI to Minikube's Docker daemon
```bash
eval $(minikube -p minikube docker-env)
```

### 3. Build the Docker image inside Minikube
```bash
docker build -t quote-api:latest .
```

### 4. Deploy to Kubernetes
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

### 5. Access the API
```bash
minikube service quote-api-service --url
```

---

## 📦 API Endpoint

- **GET** `/quote`  
Returns a random motivational quote.

```json
{
  "quote": "Consistency is the key to success."
}
```

---

## 🛠️ Tech Stack

- **FastAPI**
- **Docker**
- **Kubernetes**
- **Minikube**

---

## 📃 License

MIT — feel free to use, fork, and modify.

