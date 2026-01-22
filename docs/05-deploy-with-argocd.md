# Deploy using Argo CD (GitOps)

## 1) Apply Kyverno policies first
kubectl apply -f security/kyverno/00-namespace.yaml
kubectl apply -f security/kyverno/01-allow-approved-registries.yaml
kubectl apply -f security/kyverno/02-require-requests-limits.yaml
kubectl apply -f security/kyverno/03-disallow-latest-tag.yaml
kubectl apply -f security/kyverno/04-disallow-privileged.yaml

## 2) Create Argo CD Application
kubectl apply -f argocd/applications/secure-app-dev.yaml

## 3) Check Argo CD app
kubectl get applications -n argocd

## 4) Confirm resources created
kubectl get ns
kubectl get pods -n secure-app-dev
kubectl get svc -n secure-app-dev
