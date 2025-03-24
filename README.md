# Kubernetes with Kind (Kubernetes in Docker)

This README provides a guide for setting up a local Kubernetes cluster using **Kind** (Kubernetes in Docker) on your machine. This is useful for testing and learning Kubernetes in a lightweight, local environment.

## Prerequisites

Before setting up Kind, you need to ensure the following tools are installed on your system:

- **Docker**: Kind uses Docker to create Kubernetes clusters, so make sure Docker is installed and running.
  - [Docker Installation Guide](https://docs.docker.com/get-docker/)
  
- **Kind**: Kind is a tool for running Kubernetes clusters in Docker containers.
  - To install Kind, follow the instructions below.

## Create a Kubernetes Cluster Using Kind
``` 
kind create cluster --name kubernetes-poc
``

## Verify Cluster
```
kubectl cluster-info --context kind-kubernetes-poc
```

## Deploy an Application
```
kubectl apply -f nginx-deployment.yaml
```

## Expose the Application
```
kubectl apply -f nginx-service.yaml
```

## Access the Application
```
kubectl port-forward service/nginx-service 8080:80
```

## Delete the Cluster
```
kind delete cluster --name kubernetes-poc
```
