# kubeadm-gitops

GitOps repository for Kubernetes deployments.

## Structure

```
k8s-app/k8s/
├── 01-namespace.yaml        - Namespace definition
├── 02-mongodb-hostpath.yaml - MongoDB with persistent storage
├── 03-go-backend.yaml       - Go backend deployment & service
├── 04-react-frontend.yaml   - React frontend deployment & service
└── 04-ingress.yaml          - Ingress configuration
```

## How It Works

1. The CI/CD pipeline in `syedibrahim-dev/kubeadm` builds and tests the application
2. On successful push to `main`, it updates the image tags in this repository
3. ArgoCD watches this repository and automatically syncs changes to the cluster
