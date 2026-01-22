# Setup Local Kubernetes (Minikube)

## Install Minikube + kubectl
(If already installed, skip.)

## Start Minikube
minikube start --driver=docker

## Verify cluster
kubectl get nodes
kubectl get pods -A
