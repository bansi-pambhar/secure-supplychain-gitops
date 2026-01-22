# Install Argo CD

## Create namespace
kubectl create namespace argocd

## Install Argo CD
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

## Wait for pods
kubectl get pods -n argocd

## Access Argo CD UI (local)
kubectl port-forward svc/argocd-server -n argocd 8081:443

Open: https://localhost:8081

Browser will show warning because it is a self-signed certificate. Click:
Advanced → Proceed

## Get admin password
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

Username: admin
Password: (output above)
