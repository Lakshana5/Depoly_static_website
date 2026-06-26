# Kubernetes Static Website Deployment using Docker and Minikube

## Project Overview

This project demonstrates how to containerize a static website using Docker and deploy it on a Kubernetes cluster running on Minikube.

## Technologies Used

* Docker
* Kubernetes
* Minikube
* Nginx
* HTML

## Project Structure

```text
Depoly_static_website/
│
├── Dockerfile
├── index.html
├── deployment.yaml
├── README.md
└── images/
    ├── deployment-running.png
    └── website-output.png
```

## Prerequisites

* Docker Desktop
* Minikube
* kubectl
* Git

## Step 1: Build Docker Image

```bash
docker build -t lakshana-web:v1 .
```

Verify the image:

```bash
docker images
```

## Step 2: Load Image into Minikube

```bash
minikube image load lakshana-web:v1
```

Verify the image:

```bash
minikube image ls
```

## Step 3: Deploy the Application

```bash
kubectl apply -f deployment.yaml
```

## Step 4: Verify Kubernetes Resources

Check Nodes:

```bash
kubectl get nodes
```

Check Pods:

```bash
kubectl get pods
```

Check Deployments:

```bash
kubectl get deployments
```

Check Services:

```bash
kubectl get svc
```

## Step 5: Access the Website

Get the application URL:

```bash
minikube service web-ser --url
```

Open the generated URL in your browser.

## Deployment Output

### Kubernetes Resources

The following screenshot shows the Kubernetes node, deployment, pods, and service running successfully.

### Website Output

The following screenshot shows the static website deployed and accessed through Kubernetes.

## Kubernetes Resources Used

### Deployment

* Name: `static-website`
* Replicas: `2`
* Container Image: `lakshana-web:v1`
* Container Port: `80`

### Service

* Name: `web-ser`
* Type: `NodePort`
* Port: `80`

## Commands Used

```bash
docker build -t lakshana-web:v1 .

minikube image load lakshana-web:v1

kubectl apply -f deployment.yaml

kubectl get nodes

kubectl get pods

kubectl get deployments

kubectl get svc

minikube service web-ser --url
```

## Learning Outcomes

* Building Docker Images
* Creating Kubernetes Deployments
* Managing Pods and ReplicaSets
* Creating Kubernetes Services
* Exposing Applications using NodePort
* Running Kubernetes Locally with Minikube

##
