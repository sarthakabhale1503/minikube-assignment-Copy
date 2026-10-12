# Kubernetes & Minikube on AWS EC2

## Project Overview
This project deploys an Nginx web application on a Kubernetes cluster
running on AWS EC2 using Minikube and Docker.

## Technology Stack
- AWS EC2
- Ubuntu 26.04 LTS
- Docker Engine
- Kubernetes
- Minikube
- kubectl
- Nginx

## Architecture
- Minikube runs Kubernetes using the Docker driver.
- A Kubernetes Deployment manages two Nginx replicas.
- A NodePort Service exposes the application on port 30080.
- kubectl port-forward exposes the service through the EC2 host.

## Project Files
- nginx-deployment.yaml: Defines the Nginx Deployment with two replicas.
- nginx-service.yaml: Defines the NodePort Service on port 30080.

## Deployment Commands
Apply the manifests:

    kubectl apply -f nginx-deployment.yaml
    kubectl apply -f nginx-service.yaml

Verify the deployment:

    kubectl get nodes
    kubectl get deployments
    kubectl get pods -o wide
    kubectl get svc web-app-svc

## Configuration
- Minikube driver: Docker
- CPUs allocated: 2
- Memory allocated: 3072 MiB
- Nginx replicas: 2
- Service type: NodePort
- NodePort: 30080

## Result
The Nginx welcome page was successfully accessed through the EC2 public
IP address on port 30080.
