# Install Kyverno

## Add Helm repo
helm repo add kyverno https://kyverno.github.io/kyverno/
helm repo update

## Install Kyverno
kubectl create namespace kyverno
helm install kyverno kyverno/kyverno -n kyverno

## Verify Kyverno pods
kubectl get pods -n kyverno
