# Argo CD GitOps Manifests

This repository contains Kubernetes manifests managed through GitOps.

## NGINX application

The NGINX application is defined in [`apps/nginx/`](apps/nginx/):

- `deployment.yaml` runs two NGINX replicas with health probes and resource requests/limits.
- `service.yaml` exposes NGINX internally through a `ClusterIP` Service on port 80.

### Apply locally

```bash
kubectl apply -f apps/nginx/
kubectl get deployment,service -l app.kubernetes.io/name=nginx
```

### Access locally

```bash
kubectl port-forward service/nginx 8080:80
```

Then open <http://localhost:8080>.
