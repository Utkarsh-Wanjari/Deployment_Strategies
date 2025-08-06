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

###  Deploy Blue Environment

kubectl apply -f online-shop-without-footer-blue-deployment.yaml

###  Deploy Green Environment

kubectl apply -f online-shop-green-deployment.yaml

###  Access Applications via Port Forwarding

# Blue
kubectl port-forward --address 0.0.0.0 svc/online-shop-blue-deployment-service 30001:3001 -n blue-green-ns &

# Green
kubectl port-forward --address 0.0.0.0 svc/online-shop-green-deployment-service 30000:3000 -n blue-green-ns &

###  Switch Traffic
Edit online-shop-without-footer-blue-deployment.yaml service selector to online-shop-green, and re-apply:

kubectl apply -f online-shop-without-footer-blue-deployment.yaml

### 🌐 Access
Blue: http://<EC2_PUBLIC_IP>:30001

Green: http://<EC2_PUBLIC_IP>:30000


