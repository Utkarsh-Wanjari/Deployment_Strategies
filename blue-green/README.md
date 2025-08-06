
---

### 📄 `README.md` in `blue-green/`

Provide instructions only relevant to Blue-Green:

```markdown
# Blue-Green Deployment Strategy

This directory includes Kubernetes manifests and steps for implementing Blue-Green deployment.

---

## 🧾 Files

- `blue-green-ns.yaml`: Namespace definition
- `online-shop-without-footer-blue-deployment.yaml`: Blue environment deployment
- `online-shop-green-deployment.yaml`: Green environment deployment

---

## 🚀 Steps to Deploy

1. **Create Namespace**
   ```bash
   kubectl apply -f blue-green-ns.yaml

