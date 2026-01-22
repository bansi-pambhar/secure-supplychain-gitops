# Architecture

## Components
1. **GitHub Repo (this repo)**
   - Stores Kubernetes manifests + Kyverno policies + Argo CD Application YAML.

2. **Argo CD (in cluster)**
   - Watches this repo path: `apps/secure-app/overlays/dev`
   - Automatically applies manifests to the cluster.

3. **Kyverno (in cluster)**
   - Acts as an admission controller.
   - Validates workloads BEFORE they run.
   - Blocks insecure pods.

## GitOps Flow
1. You commit YAML changes to GitHub
2. Argo CD detects changes
3. Argo CD syncs changes to Kubernetes
4. Kyverno enforces policies on new/updated Pods
