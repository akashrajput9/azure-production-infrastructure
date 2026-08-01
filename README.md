# Azure Production Platform

> A production-ready Azure infrastructure for deploying containerized Laravel applications using Infrastructure as Code (Terraform), Azure Kubernetes Service (AKS), Docker, and GitHub Actions.

![Azure](https://img.shields.io/badge/Azure-Cloud-blue)
![Terraform](https://img.shields.io/badge/Terraform-IaC-7B42BC)
![Docker](https://img.shields.io/badge/Docker-Containers-2496ED)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-326CE5)
![Laravel](https://img.shields.io/badge/Laravel-PHP-FF2D20)
![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-2088FF)

---

## Overview

This repository demonstrates a production-oriented deployment platform for Laravel applications on Microsoft Azure. The infrastructure is fully provisioned using Terraform and designed around modern DevOps practices including containerization, Infrastructure as Code, automated CI/CD, secure secret management, monitoring, and scalable Kubernetes deployments.

The objective of this project is to showcase how cloud infrastructure and application deployment can be managed consistently, securely, and efficiently using industry-standard tools.

---

# Architecture

```text
                           Internet
                               │
                         Cloudflare CDN
                               │
                    Azure Application Gateway
                         (WAF Enabled)
                               │
                  Azure Kubernetes Service (AKS)
                 ┌──────────────┴──────────────┐
                 │                             │
           Laravel API                  Queue Worker
                 │                             │
                 └──────────────┬──────────────┘
                                │
                           Redis Cache
                                │
                   Azure Database for MySQL
                                │
                      Azure Key Vault
                                │
                  Azure Monitor & Application Insights
```

---

# Project Goals

- Provision Azure infrastructure using Terraform
- Deploy Laravel applications on Kubernetes
- Automate deployments using GitHub Actions
- Secure secrets with Azure Key Vault
- Implement monitoring and logging
- Demonstrate production deployment practices
- Build reusable cloud infrastructure

---

# Features

- Infrastructure as Code (Terraform)
- Azure Kubernetes Service (AKS)
- Dockerized Laravel Application
- Azure Container Registry (ACR)
- GitHub Actions CI/CD
- Rolling Deployments
- Horizontal Pod Autoscaler
- Health Checks
- Azure Key Vault Integration
- Managed Identity Authentication
- Azure Application Gateway with WAF
- Redis Caching
- Queue Workers
- Scheduled Jobs
- Prometheus Monitoring
- Grafana Dashboards
- Centralized Logging
- Kubernetes Network Policies
- RBAC Security
- Disaster Recovery Documentation

---

# Technology Stack

## Cloud

- Microsoft Azure
- Azure Kubernetes Service
- Azure Container Registry
- Azure Database for MySQL
- Azure Key Vault
- Azure Application Gateway
- Azure Monitor
- Azure Virtual Network

## Infrastructure

- Terraform

## Containers

- Docker
- Kubernetes
- Helm

## CI/CD

- GitHub Actions

## Application

- Laravel
- PHP
- Nginx
- Redis
- MySQL

## Monitoring

- Prometheus
- Grafana

---

# Repository Structure

```text
azure-production-platform
│
├── .github/
│   └── workflows/
│       ├── ci.yml
│       ├── cd.yml
│       └── security.yml
│
├── architecture/
│
├── docker/
│
├── terraform/
│   ├── environments/
│   ├── modules/
│   ├── providers.tf
│   ├── variables.tf
│   ├── outputs.tf
│   ├── versions.tf
│   └── main.tf
│
├── kubernetes/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── ingress.yaml
│   ├── namespace.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   ├── hpa.yaml
│   └── networkpolicy.yaml
│
├── helm/
│
├── monitoring/
│
├── scripts/
│
├── docs/
│
├── images/
│
├── README.md
│
└── LICENSE
```

---

# Infrastructure Components

| Component | Description |
|-----------|-------------|
| Azure Virtual Network | Private networking for Azure resources |
| Application Gateway | Layer 7 Load Balancer with Web Application Firewall |
| Azure Kubernetes Service | Container orchestration platform |
| Azure Container Registry | Docker image repository |
| Azure Database for MySQL | Managed relational database |
| Azure Key Vault | Secret and certificate management |
| Redis | Cache and queue backend |
| Azure Monitor | Metrics and logging |
| Prometheus | Kubernetes monitoring |
| Grafana | Visualization dashboards |

---

# Deployment Workflow

```text
Developer

      │
      ▼

Git Push

      │
      ▼

GitHub Actions

      │
      ▼

Run Tests

      │
      ▼

Build Docker Image

      │
      ▼

Push Image to Azure Container Registry

      │
      ▼

Deploy to Azure Kubernetes Service

      │
      ▼

Rolling Update

      │
      ▼

Health Checks

      │
      ▼

Deployment Completed
```

---

# Security

The platform follows several security best practices:

- Azure Managed Identity
- Azure Key Vault for secrets
- Kubernetes Secrets
- Network Policies
- Role-Based Access Control (RBAC)
- HTTPS Encryption
- Web Application Firewall (WAF)
- Least Privilege Principle
- Secure Container Images

---

# Monitoring

Monitoring is implemented using:

- Azure Monitor
- Azure Application Insights
- Prometheus
- Grafana
- Kubernetes Metrics Server

The dashboards provide visibility into:

- CPU Utilization
- Memory Usage
- Pod Status
- Node Health
- Application Availability
- Request Latency
- Error Rates

---

# CI/CD Pipeline

The GitHub Actions workflow performs the following steps:

1. Checkout source code
2. Install dependencies
3. Execute automated tests
4. Build Docker image
5. Scan container image
6. Push image to Azure Container Registry
7. Deploy to AKS
8. Verify rollout
9. Complete deployment

---

# Scalability

The platform is designed to support:

- Horizontal Pod Autoscaling
- Rolling Deployments
- Self-Healing Containers
- High Availability
- Load Balancing
- Readiness Probes
- Liveness Probes

---

# Disaster Recovery

Documentation includes:

- Infrastructure recreation using Terraform
- Database backup strategy
- Cluster recovery
- Secret restoration
- Rollback procedures
- Deployment recovery

---

# Documentation

The `docs` directory contains:

- Deployment Guide
- Security Guide
- Disaster Recovery Plan
- Scaling Strategy
- Cost Optimization Guide
- Operational Runbooks

---

# Future Improvements

Planned enhancements include:

- Argo CD (GitOps)
- Azure Front Door
- Blue/Green Deployments
- Canary Releases
- OpenTelemetry
- Multi-Region Deployment
- Infrastructure Cost Reports
- Azure Policy Integration

---

# Getting Started

Clone the repository.

```bash
git clone https://github.com/akashrajput9/azure-production-infrastructure.git
```

Navigate into the project.

```bash
cd azure-production-platform
```

Initialize Terraform.

```bash
terraform init
```

Review the execution plan.

```bash
terraform plan
```

Apply the infrastructure.

```bash
terraform apply
```

Build the application image.

```bash
docker build -t laravel-app .
```

Deploy the application to Kubernetes.

```bash
kubectl apply -f kubernetes/
```

---

# Contributing

Contributions, suggestions, and improvements are welcome. Feel free to open an issue or submit a pull request.

---

# License

This project is licensed under the MIT License.

---

# Author

**Akash Ahmed**

Senior DevOps Engineer

Azure • AWS • Kubernetes • Docker • Terraform • GitHub Actions • Laravel

---

## Disclaimer

This project is intended for educational and portfolio purposes. It demonstrates production-oriented architecture and deployment practices. Before using it in a live environment, infrastructure sizing, security configurations, networking, and operational procedures should be reviewed and adapted according to business requirements.