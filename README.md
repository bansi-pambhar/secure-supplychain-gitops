# Secure Supply Chain GitOps (Argo CD + Kyverno)

This repository is a complete GitOps-based Kubernetes deployment portfolio project.

## What this project demonstrates
- **GitOps**: Git repository is the source of truth for Kubernetes desired state.
- **Argo CD**: Automatically syncs and deploys manifests from this repo to Kubernetes.
- **Kyverno**: Enforces security policies (DevSecOps / policy-as-code).

## Repository layout
- `apps/secure-app/` → Kubernetes manifests for the sample app (Kustomize base + overlay)
- `security/kyverno/` → Kyverno ClusterPolicies for security enforcement
- `argocd/applications/` → Argo CD Application manifest to deploy the dev environment
- `docs/` → Step-by-step setup and troubleshooting

## Quick start (local)
Follow in order:
1. `docs/02-setup-local-cluster.md`
2. `docs/03-install-argocd.md`
3. `docs/04-install-kyverno.md`
4. `docs/05-deploy-with-argocd.md`
5. `docs/06-verify-policies.md`

## Author
Bansi Pambhar

