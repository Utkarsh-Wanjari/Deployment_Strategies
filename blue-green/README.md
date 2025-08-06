# 🟦🟩 Blue-Green Deployment Strategy

This directory includes Kubernetes manifests and steps for implementing the **Blue-Green Deployment Strategy** in a Kubernetes environment using EKS.

---

## 📁 Files

- `blue-green-ns.yaml`: Namespace definition
- `online-shop-without-footer-blue-deployment.yaml`: Blue environment deployment
- `online-shop-green-deployment.yaml`: Green environment deployment

---

## 🚀 Steps to Deploy

### 1. Create Namespace

kubectl apply -f blue-green-ns.yaml

