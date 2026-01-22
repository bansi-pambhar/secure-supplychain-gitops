# Verify Kyverno Policies

## Check policies
kubectl get clusterpolicies

## Test 1: Try an image that is NOT allowed (example: docker.io)
kubectl run bad1 --image=docker.io/library/busybox --restart=Never -n secure-app-dev

Expected: blocked by Kyverno (registry restriction)

## Test 2: Try nginx:latest (latest tag blocked)
kubectl run bad2 --image=nginx:latest --restart=Never -n secure-app-dev

Expected: blocked by Kyverno (no latest)

## Test 3: Try allowed image with tag + requests/limits
kubectl run good1 --image=nginx:1.25 --restart=Never -n secure-app-dev \
  --requests='cpu=50m,memory=64Mi' --limits='cpu=100m,memory=128Mi'

Expected: allowed (depends on kubectl version support for flags; otherwise use a YAML pod manifest)
