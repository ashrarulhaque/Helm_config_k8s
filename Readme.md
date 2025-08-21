```markdown
# 🚀 MERN App Helm Chart with Ingress

This repository contains a Helm chart for deploying a full-stack **MERN (MongoDB, Express, React, Node.js)** application on Kubernetes with **Ingress + optional TLS**.

---

## 📂 Chart Structure

```

mern-app/
├── templates/
│   ├── deployment-frontend.yaml
│   ├── service-frontend.yaml
│   ├── deployment-backend.yaml
│   ├── service-backend.yaml
│   ├── mongodb-service.yaml
│   ├── pvc-mongodb.yaml
│   ├── ingress.yaml
├── values.yaml
├── Chart.yaml
└── README.md

````

---

## 🌍 Features
- Deploys **React frontend**, **Node.js backend**, and **MongoDB database**
- Exposes via **Ingress Controller** (NGINX recommended)
- Supports **TLS certificates**
- Configurable via `values.yaml`

---

## ⚙️ Prerequisites
- Kubernetes cluster
- Helm 3+
- NGINX Ingress Controller  
  ```bash
  helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
  helm install ingress-nginx ingress-nginx/ingress-nginx
````

* (Optional) Cert-Manager for Let’s Encrypt TLS

## 📊 Architecture Diagram

```mermaid
flowchart TD
    A[User Browser] --> B[Ingress Controller (NGINX)]
    B --> C[Frontend Service (React + Nginx)]
    B --> D[Backend Service (Node.js + Express)]
    D --> E[(MongoDB StatefulSet + PVC)]
```

---

## 🌐 Access the App

* React frontend → `https://mern.example.com/`
* Node backend → `https://mern.example.com/api`
* MongoDB → Internal only (ClusterIP)

---

## 📖 References

* [Helm Docs](https://helm.sh/docs/)
* [NGINX Ingress Controller](https://kubernetes.github.io/ingress-nginx/)
* [Cert-Manager](https://cert-manager.io/docs/)

```
