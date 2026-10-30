# Argo CD Kubernetes GitOps

This repository stores Kubernetes manifests managed by Argo CD.

Git is the source of truth for our Kubernetes infrastructure.

## Applications

### NGINX

Location: `apps/nginx/`

Resources:

- Namespace
- Deployment
- Service

Configuration:

- 2 replicas
- Rolling updates
- Readiness and liveness probes
- CPU and memory requests/limits
- Internal ClusterIP service

## Deployment

Argo CD monitors this repository and synchronizes
the Kubernetes resources with the desired state
defined in Git.

## Architecture

GitHub → Argo CD → Kubernetes