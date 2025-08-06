# Kubernetes Deployment Strategies

This repository demonstrates two major deployment strategies in Kubernetes:

- **Blue-Green Deployment**
- **Rolling Update Deployment**

Each strategy is contained in its own directory with proper YAML manifests and step-by-step instructions.

---

## 📁 Contents

| Strategy        | Description                                 | Folder         |
|----------------|---------------------------------------------|----------------|
| Blue-Green      | Two environments (Blue & Green) with manual traffic switch. | `blue-green/`   |
| Rolling Update  | Gradual rollout of pods using deployment strategy.         | `rolling-update/` |

---

## 🧰 Prerequisites

- AWS EC2 instance (Ubuntu)
- AWS CLI configured
- Docker installed
- `eksctl` and `kubectl` installed
- IAM role with Admin access attached to EC2 instance

---

## 📦 Setup Tools

```bash
# Docker
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker && sudo systemctl enable docker

# AWS CLI
aws configure

# kubectl
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.32.3/2025-04-17/bin/linux/amd64/kubectl
chmod +x ./kubectl
mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH
echo 'export PATH=$HOME/bin:$PATH' >> ~/.bashrc

# eksctl
ARCH=amd64
PLATFORM=$(uname -s)_$ARCH
curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"
tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp && rm eksctl_$PLATFORM.tar.gz
sudo install -m 0755 /tmp/eksctl /usr/local/bin

☁️ Create EKS Cluster
eksctl create cluster --name irondome --node-type t2.medium --nodes 2 --region us-east-1

🧹 Clean Up
 eksctl delete cluster --name <cluster-name> --region <region>



