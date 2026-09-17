```bash
kubectl create namespace lab-01-helm-dev --dry-run=client -o yaml | kubectl apply -f -
kubectl create namespace lab-01-helm-stage --dry-run=client -o yaml | kubectl apply -f -
kubectl create namespace lab-01-helm-prod --dry-run=client -o yaml | kubectl apply -f -
```

## Install Dev

```bash
helm install guestbook helm-guest-book \
  --namespace lab-01-helm-dev
```

### Install stage

```bash
helm install guestbook helm-guest-book \
  --namespace lab-01-helm-stage \
  --set replicaCount=3 \
  --set greeting="Hello from stage"
```

### Install prod

```bash
helm install guestbook helm-guest-book \
  --namespace lab-01-helm-stage \
  --set replicaCount=10 \
  --set greeting="Hello from stage"
```
