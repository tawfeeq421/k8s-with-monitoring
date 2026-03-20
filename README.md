# 📦 Kubernetes Ingress Project (Multi-App with TLS)

This repository contains Kubernetes manifests to deploy multiple applications and expose them using **Ingress (Host-based & Path-based routing)** with **TLS (HTTPS)** support.

---

## 📁 Project Structure

```bash
.
├── login/
│   ├── login-app-deployment.yml
│   └── login-app-service.yml  
├── realstate/
│   ├── realstate-app-deployment.yml
│   └── realstate-app-service.yml 
├── tourist/
│   ├── tourist-app-deployment.yml
│   └── tourist-app-service.yml 
├── host-based-ingress.yml
├── path-based-ingress.yml
├── namespace.yml
├── secret.yml
```

---

## 🛠️ Technologies Used

* Kubernetes (K8s)
* Docker
* NGINX Ingress Controller
* YAML (Kubernetes Manifests)
* TLS/SSL Certificates
* Linux (for deployment & testing)

---

## 🌐 Routing Strategies

### 1️⃣ Path-Based Routing 🔹

* Routes traffic based on URL paths

**Example:**

* `/login` → Login App
* `/realstate` → Real Estate App
* `/tourist` → Tourist App

---

### 2️⃣ Host-Based Routing 🔹

* Routes traffic based on domain names

**Example:**

* `login.example.com` → Login App
* `realstate.example.com` → Real Estate App
* `tourist.example.com` → Tourist App

---

## ⚙️ Setup Instructions

### 1️⃣ Create Namespace

```bash
kubectl apply -f namespace.yml
```

---

### 2️⃣ Deploy Applications

```bash
kubectl apply -f login/
kubectl apply -f realstate/
kubectl apply -f tourist/
```

---

### 3️⃣ Install Ingress Controller

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
```

---

### 4️⃣ Create TLS Secret

```bash
kubectl create secret tls amazon-tls \
  --cert=cert.crt \
  --key=key.key \
  -n prod
```

---

### 5️⃣ Configure Hosts File (For Local Testing)

Edit:

* Linux/Mac → `/etc/hosts`
* Windows → `C:\Windows\System32\drivers\etc\hosts`

```bash
<YOUR_NODE_IP> login.example.com
<YOUR_NODE_IP> realstate.example.com
<YOUR_NODE_IP> tourist.example.com
```

---

## 🌍 Access Application

### 🔹 Host-Based Access

* [https://login.example.com](https://login.example.com)
* [https://realstate.example.com](https://realstate.example.com)
* [https://tourist.example.com](https://tourist.example.com)

### 🔹 Path-Based Access

* https://<IP>/login
* https://<IP>/realstate
* https://<IP>/tourist

---

## 🔐 Features

* Multi-application deployment on Kubernetes
* Host-based and Path-based routing
* TLS/HTTPS secure communication
* Namespace isolation
* Scalable microservices architecture

---

## 🧠 Key Learnings

* Kubernetes Ingress concepts
* Difference between Host-based and Path-based routing
* Managing multiple apps in a single cluster
* TLS configuration in Kubernetes
* Writing structured YAML manifests

---

## 🚀 Future Improvements

* Add Helm charts for easier deployment
* Integrate cert-manager for automatic SSL
* Implement CI/CD pipeline (GitHub Actions / Jenkins)
* Add monitoring (Prometheus & Grafana)
* Deploy on cloud (AWS / GCP / Azure)

---

## 👨‍💻 Author

**Tawfeeq Ahmed**

---

## ⭐ Support

If you found this project helpful:

* ⭐ Star this repository
* 🍴 Fork and contribute
* 📢 Share with others

---
