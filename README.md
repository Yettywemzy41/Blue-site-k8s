# Blue Site Kubernetes Deployment

A multi-replica web application demonstrating different Kubernetes Service types for local and external access.

## Architecture
- **Deployment**: 3 replicas of `damsconas/blue-site:latest` running on port 5000.
- **Scaling**: Managed via the `replicas: 3` field in the deployment manifest.

---

## Service Types Explored

### 1. NodePort (`service-nodeport.yml`)
- **Function**: Exposes the service on a static port (30008) on the Node's IP.
- **Access**: `http://localhost:30008`
- **Use Case**: Best for internal testing where a specific, predictable port is required.

### 2. LoadBalancer (`service-loadbalancer.yml`)
- **Function**: Provisions an external Load Balancer (simulated via Docker Desktop) to route traffic to the pods.
- **Access**: `http://localhost` (Port 80) or `http://[Mac-IP]` for external devices on the same Wi-Fi.
- **Use Case**: Best for production-like environments where you want standard web access and automatic traffic distribution.

---

## How to Deploy
1. Apply the deployment:
   `kubectl apply -f deployment.yml`
2. Apply your choice of service:
   `kubectl apply -f service-loadbalancer.yml`
