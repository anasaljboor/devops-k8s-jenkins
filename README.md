# # Kubernetes CI/CD Pipeline — Jenkins + Docker + K8s

A fully automated CI/CD pipeline that builds, pushes, and deploys a containerized web application to a multi-node Kubernetes cluster using Jenkins.

---

## Pipeline Overview

```
Git Push → Jenkins → Docker Build → Docker Hub → Kubernetes Deployment
```

### Stages

| Stage | Description |
|-------|-------------|
| Git Checkout | Pulls latest code from GitHub repository |
| Build | Builds Docker image and tags it (`anasaljboor/anas:v2`) |
| Push | Pushes image to Docker Hub |
| Deploy | Applies Kubernetes manifests to the cluster via `kubectl` |

---

## Infrastructure

The Kubernetes cluster was set up on **RHEL** following a multi-node architecture:

- 1 Control Plane node
- Multiple Worker Nodes

**Cluster setup reference:** [How to Install Kubernetes Cluster on RHEL](https://www.linuxtechi.com/how-to-install-kubernetes-cluster-rhel/)

---

## Kubernetes Configuration

**Deployment (`deployments.yml`)**
- 3 replicas of the application pod
- Image: `anasaljboor/anas:v2`
- Container port: 80

**Service (`svc-nodeportvip.yml`)**
- NodePort service for external access to the application

---

## Tech Stack

| Tool | Role |
|------|------|
| Jenkins | CI/CD orchestration |
| Docker | Containerization & image registry (Docker Hub) |
| Kubernetes | Container orchestration (multi-node, RHEL) |
| kubectl | Cluster management & deployment |
| GitHub | Source code management |

---

## Application

The deployed application (`2126_antique_cafe/`) is a static web app used as the target workload to demonstrate the full pipeline from source code to running container on Kubernetes.

---

## Author

**Anas Al Jboor**  
Computer Science Student | DevOps & Cloud Engineering  
