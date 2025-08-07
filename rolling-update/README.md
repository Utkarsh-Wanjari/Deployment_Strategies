
---

### 📄 `README.md` in `rolling-update/`

```markdown
# Rolling Update Deployment Strategy

This directory demonstrates how to perform a rolling update in Kubernetes.

---

## 🧾 Files

- `rolling-namespace.yml`
- `rolling-update-deployment.yaml`
- `rolling-update-svc.yml`

---

## 🚀 Steps to Deploy

1. ### Create Namespace

   kubectl apply -f rolling-namespace.yml

2. ### Deploy Application

   kubectl apply -f rolling-update-deployment.yaml
   kubectl apply -f rolling-update-svc.yml

3. ### Port Forwarding

   kubectl port-forward --address 0.0.0.0 svc/rolling-update-service 3000:3000 -n rolling-ns &

4. ### Monitor (open in new terminal)

   watch kubectl get pods -n rolling-ns

5. ### Rolling Update

    Modify deployment image and re-apply:
    image: utkarsh1313/online_shop
   To:
     mage: utkarsh1313/online_shop_without_footer

    kubectl apply -f rolling-update-deployment.yaml


### 🌐 Access
     URL: http://<EC2_PUBLIC_IP>:3000







