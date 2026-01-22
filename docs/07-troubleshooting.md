# Troubleshooting

## Argo CD pods pending / container creating
kubectl get pods -n argocd
Wait 1-2 minutes or check cluster resources.

## Argo CD UI shows privacy warning
This is normal for self-signed TLS.
Click Advanced → Proceed

## Argo says "app path does not exist"
Check the Application manifest `spec.source.path` matches repo path:
apps/secure-app/overlays/dev

## Kyverno blocking deployment
Check policy messages:
kubectl describe clusterpolicy <policy-name>
kubectl get events -n secure-app-dev --sort-by=.metadata.creationTimestamp
