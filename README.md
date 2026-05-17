# Cloud-Native Product Catalog Platform

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE) [![Docker](https://img.shields.io/badge/stack-Docker%20%7C%20Kubernetes-blue)](#) [![Node.js](https://img.shields.io/badge/lang-Node.js-green)](#) [![Kubernetes](https://img.shields.io/badge/orchestration-Kubernetes-blueviolet)](#)



This repository contains a production-oriented sample application and infrastructure manifests that illustrate containerization, local multi-container development, and Kubernetes deployments. It is intended as a learning and reference project for teams implementing cloud-native patterns.

## Table of Contents

1. [Overview](#overview)
2. [Repository Structure](#repository-structure)
3. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Running Locally with Docker Compose](#running-locally-with-docker-compose)
   - [Deploying on Kubernetes](#deploying-on-kubernetes)
4. [Features](#features)

---

## Overview

A minimal, well-documented Node.js web application used to demonstrate container-based development and Kubernetes deployment patterns. The project includes:

- Container image build instructions via `Dockerfile`
- Local multi-container development via `compose.yaml`
- Kubernetes manifests for simple and more advanced deployments in `k8s/`
- Example Helm packaging in `k8s/helm-chart`

This repository is useful for learning, demos, and rapid prototyping of cloud-native deployment workflows.

---

## Repository Structure

Top-level layout (high level):

```
.
├── .dockerignore
├── Dockerfile
├── compose.yaml            # Local development (Docker Compose)
├── app.js                  # Node.js application
├── package.json
├── k8s/
│   ├── basic/              # Simple manifests (Pod, Service)
│   ├── deployments/        # Production-like Deployment manifests
│   └── helm-chart/         # Example Helm chart
├── public/
└── views/
```

### Highlights

- **`Dockerfile`**: Defines the base image and steps required to run the Node.js application.
- **`compose.yaml`**: Illustrates a multi-container setup, including a database, for local development.
- **`k8s/`**: Contains everything Kubernetes-related, including:
    - **basic**: Simple resource manifests (Pods, Services).
    - **deployments**: More advanced deployments or stateful sets.
    - **helm-chart**: Helm-based packaging for easier versioning and reusable deployment configurations.
- **`app.js`**: Node.js application logic to demonstrate a minimal web service.

---

## Getting Started

### Prerequisites

You’ll need the following installed on your machine:

- Node.js (optional if you just want to run via Docker)
- Docker
- Docker Compose
- Kubernetes CLI (kubectl)
- Helm (optional) for using Helm charts

### Running Locally with Docker Compose

1. **Clone this repository**:

    ```bash
    git clone https://github.com/snkshukla/masterclass-sample.git
    cd masterclass-sample
    ```

2. **Build and run the containers**:

    ```bash
    docker-compose -f compose.yaml up --build
    ```

3. **Access your application**:

    Open your browser and go to:

    ```
    http://localhost:3000
    ```

    You should see the Node.js application up and running, connected to its database (if configured in the Compose file).


### Deploying on Kubernetes

> Note: Make sure you have a running Kubernetes cluster (either a local tool like minikube, Kind or a cloud provider).
>
1. **Apply the basic Kubernetes manifests** (in the `k8s/basic` folder):

    ```bash
    kubectl apply -f k8s/basic/
    ```

2. **Check the status**:

    ```bash
    kubectl get pods
    kubectl get services
    ```

3. **(Optional) Port Forward** to access the service locally:

    ```bash
    kubectl port-forward svc/web 3000:3000
    ```

4. **Open your browser** to http://localhost:3000 to see the running application.
5. **Explore advanced Kubernetes** deployments in the `k8s/deployments` folder, or try **Helm charts** in `k8s/helm-chart` to package and deploy your application more efficiently.

---



<div align="center">

**Made with ❤️ by M Harish Gautham**

⭐ If you find this project helpful, please star it! ⭐

[Website](https://github.com/harishy0406/Cloud-Native-Product-Catalog-Platform) • [Docs](https://github.com/harishy0406/Cloud-Native-Product-Catalog-Platform) • [GitHub](https://github.com/harishy0406/Cloud-Native-Product-Catalog-Platform)

</div>
