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

Install the tools required for local development and Kubernetes deployments:

- Docker (or Docker Desktop)
- Docker Compose (or Docker Compose V2 via `docker compose`)
- kubectl (Kubernetes CLI)
- Optional: Helm for chart packaging

### Quickstart — Docker Compose

Clone the repository and start the local services with build:

```bash
git clone https://github.com/harishy0406/Cloud-Native-Product-Catalog-Platform.git
cd Cloud-Native-Product-Catalog-Platform
docker compose -f compose.yaml up --build
```

Open http://localhost:3000 in your browser.


---


<div align="center">

**Made with ❤️ by M Harish Gautham**

⭐ If you find this project helpful, please star it! ⭐

[Website](https://github.com/harishy0406/Cloud-Native-Product-Catalog-Platform) • [Docs](https://github.com/harishy0406/Cloud-Native-Product-Catalog-Platform) • [GitHub](https://github.com/harishy0406/Cloud-Native-Product-Catalog-Platform)

</div>
