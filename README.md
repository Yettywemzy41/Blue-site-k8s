# Blue-site-k8s
This project deploys a 3-replica web application to a Kubernetes cluster.

## Architecture
- **Deployment**: 3 replicas of `damsconas/blue-site`.
- **Service**: NodePort exposing the app on port 30008.

## How to Run
1. Ensure Docker Desktop (Kubernetes) is running.
2. Apply the manifests:
   ```bash
   kubectl apply -f .
Access at http://localhost:30008
