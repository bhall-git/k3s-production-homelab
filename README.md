# k3s Production Homelab

Production-style Kubernetes homelab built on a Raspberry Pi 5 using Ubuntu Server and k3s. This project was created to strengthen hands-on operational troubleshooting, Kubernetes administration, monitoring, Linux systems, and infrastructure management skills.

---

# Overview

This environment simulates a lightweight production Kubernetes platform with:

* Kubernetes orchestration using k3s
* Ingress routing with Traefik
* Monitoring and observability using Prometheus and Grafana
* Remote Kubernetes administration using kubectl
* Infrastructure version control with Git and GitHub
* Linux system administration and troubleshooting workflows

The project is designed to provide practical experience with:

* Kubernetes deployments
* Linux troubleshooting
* Monitoring and observability
* Networking and ingress routing
* Helm package management
* SSH authentication and Git workflows
* Production support concepts

---

# Architecture

```text
                ┌──────────────────────┐
                │   Local Workstation  │
                │ kubectl / Git / SSH  │
                └──────────┬───────────┘
                           │
                    Remote Access
                           │
                ┌──────────▼───────────┐
                │ Raspberry Pi 5       │
                │ Ubuntu Server        │
                │ k3s Kubernetes       │
                └──────────┬───────────┘
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
 ┌──────▼──────┐   ┌──────▼──────┐   ┌──────▼──────┐
 │  Traefik    │   │ Prometheus  │   │   Grafana   │
 │  Ingress    │   │ Monitoring  │   │ Dashboards  │
 └──────┬──────┘   └─────────────┘   └─────────────┘
        │
 ┌──────▼──────┐
 │ NGINX App   │
 │ Deployment  │
 └─────────────┘
```

---

# Technologies Used

| Technology     | Purpose                             |
| -------------- | ----------------------------------- |
| Ubuntu Server  | Base operating system               |
| Raspberry Pi 5 | Hardware platform                   |
| k3s            | Lightweight Kubernetes distribution |
| Kubernetes     | Container orchestration             |
| Traefik        | Ingress controller                  |
| Helm           | Kubernetes package manager          |
| Prometheus     | Metrics collection                  |
| Grafana        | Monitoring dashboards               |
| Git            | Version control                     |
| GitHub         | Repository hosting                  |
| SSH            | Secure remote access                |

---

# Current Features

## Kubernetes Cluster

* Single-node k3s Kubernetes cluster
* Remote kubectl administration
* Namespace organization
* Deployment and Service management

## Application Deployment

* NGINX deployment using Kubernetes manifests
* Kubernetes Service exposure
* Ingress routing using Traefik

## Monitoring & Observability

* Prometheus monitoring stack
* Grafana dashboards
* Node and pod metrics
* Kubernetes cluster observability

## GitOps / Repository Management

* Infrastructure repository hosted on GitHub
* SSH-based Git authentication
* Version-controlled Kubernetes manifests

---

# Repository Structure

```text
k3s-production-homelab/
├── kubernetes/
│   ├── apps/
│   ├── ingress/
│   └── monitoring/
├── docs/
├── screenshots/
└── README.md
```

---

# Kubernetes Components

## Namespaces

| Namespace   | Purpose                  |
| ----------- | ------------------------ |
| apps        | Application workloads    |
| monitoring  | Monitoring stack         |
| kube-system | Core Kubernetes services |

---

# Monitoring Stack

The monitoring environment was deployed using Helm and the kube-prometheus-stack chart.

Components include:

* Prometheus
* Grafana
* Alertmanager
* kube-state-metrics
* node-exporter

Monitoring capabilities:

* Node CPU and memory metrics
* Pod resource usage
* Kubernetes cluster health
* Workload observability

---

# Troubleshooting & Lessons Learned

During development and deployment, several operational issues were encountered and resolved:

## Kubernetes / Helm

* kubeconfig permission issues
* Helm repository configuration problems
* Kubernetes cluster connectivity troubleshooting
* Environment variable configuration (`KUBECONFIG`)

## Linux / System Administration

* File ownership and permission management
* SSH key generation and authentication
* Bash environment persistence using `.bashrc`
* Networking and ingress troubleshooting

## Git / GitHub

* SSH authentication setup
* GitHub email privacy restrictions
* Git configuration and commit identity management

---

# Example Commands

## Cluster Health

```bash
kubectl get nodes
kubectl get pods -A
helm ls -A
```

## Monitoring

```bash
kubectl get pods -n monitoring
kubectl port-forward svc/monitoring-grafana -n monitoring 3000:80
```

## Application Deployment

```bash
kubectl apply -f nginx-deployment.yaml
kubectl apply -f nginx-service.yaml
kubectl apply -f nginx-ingress.yaml
```

---

# Future Improvements

Planned enhancements include:

* Centralized logging using Loki and Promtail
* HTTPS/TLS configuration
* CI/CD pipeline integration
* Multi-node Kubernetes cluster
* Automated backups
* Alerting and notification workflows
* Infrastructure automation

---

# Screenshots

Screenshots will be added for:

* Grafana dashboards
* Kubernetes workloads
* Ingress routing
* Cluster monitoring
* kubectl output

---

# Key Skills Demonstrated

* Linux administration
* Kubernetes operations
* Infrastructure troubleshooting
* Monitoring and observability
* Networking and ingress management
* Helm package deployment
* Git and GitHub workflows
* SSH authentication and security
* Production support concepts

---

# Purpose of This Project

This project was built to strengthen practical operational and troubleshooting skills relevant to:

* Production Support Engineering
* DevOps Engineering
* Site Reliability Engineering (SRE)
* Cloud Operations
* Platform Engineering

The focus is on hands-on experience with deployment, monitoring, troubleshooting, and operational workflows in a Kubernetes environment.


