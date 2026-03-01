# Kubernetes (K8s) – Basic Overview & Implementation

## 📌 What is Kubernetes?
Kubernetes (K8s) is an open-source container orchestration tool.  
It is used to deploy, manage, scale, and run containerized applications automatically.

Kubernetes helps us:
- Run applications reliably
- Scale applications easily
- Manage containers efficiently

---

## 🎯 Why Kubernetes is Used?
Kubernetes is used to:
- Handle multiple containers
- Auto-scale applications (increase/decrease pods)
- Maintain high availability
- Manage load traffic
- Reduce downtime using rolling updates

---

## 🛠️ What We Do in Kubernetes?
In this project, we work with the following Kubernetes concepts:

- **Pods** – Smallest unit in Kubernetes
- **Deployments** – Manage pods and replicas
- **Services** – Expose applications
- **Namespaces** – Logical separation of resources
- **ReplicaSets** – Maintain desired pod count
- **Horizontal Scaling** – Increase/decrease pods
- **Rolling Update** – Update app without downtime

---

## 📂 Kubernetes Components Used
- Pod
- Deployment
- Service
- Namespace
- Ingress
- ConfigMap (optional)
- Secrets (optional)

---

## 🔄 Deployment Strategy Used
### Rolling Update
Rolling update allows updating the application gradually.
- No downtime
- Old pods are replaced step by step
- Application remains available

---

## 📈 Scaling in Kubernetes
### Horizontal Scaling
- Automatically or manually increase pods
- Helps handle more traffic
- Improves performance

Command example:
```bash
kubectl scale deployment app-name --replicas=3
