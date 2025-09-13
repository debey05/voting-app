# Voting Application Deployment Project

This project was completed to deploy a **Voting Application** for a vet company.

---

## Workflow Overview

### 1. Code Management & CI
- Developers push the code to the **GitHub repository**.
- **GitHub Actions** is configured to run Continuous Integration (CI) upon each push.
- **SonarQube** checks the code for:
  - Vulnerabilities  
  - Code duplication  
  - Code smells  
- Code must pass defined **quality gates**.  
  - ❌ If any check fails → CI fails.  
  - ✅ If successful → CI continues.  

### 2. Docker Build & Registry
- Once quality checks pass, **Docker images** are built.  
- Images are then pushed to the **Docker Hub repository**.  
- These images are later pulled for Continuous Deployment (CD).

### 3. Continuous Deployment with ArgoCD
- **Argo CD** fetches Kubernetes manifest files from the GitHub repository.  
- It then deploys the images to the **Kubernetes cluster**.  
- Using a **NodePort cluster network**, the deployed application is made accessible to frontend clients via their browser.

### 4. Monitoring & Observability
- **Prometheus** scrapes real-time cluster data such as:
  - Node health  
  - Pod status  
  - Resource utilization (CPU, memory, disk)  
  - Network metrics  
- **Grafana** visualizes this data on dashboards, providing a quick view of cluster performance and health.

---

## Architecture Highlights
- **GitHub Actions** → CI pipeline  
- **SonarQube** → Code quality enforcement  
- **Docker Hub** → Image registry  
- **Argo CD** → GitOps-based deployment to Kubernetes  
- **Prometheus + Grafana** → Monitoring and visualization

---






example of the various types of pieces and languages you might see (queues, persistent data, etc), and how to
deal with them in Docker at a basic level.
