# k8s

## ArgoCD

Requirements
Installed [kubectl](https://kubernetes.io/docs/tasks/tools/) command-line tool.


## Getting Started ArgoCD

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/core-install.yaml
```

```
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
```
## Port Forwarding

```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
```
http://localhost:8080

```

## Secret

```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```