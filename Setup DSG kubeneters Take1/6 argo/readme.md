Argo CD

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

```

Watch all pods Running
```
watch kubectl get pods -n argocd
```

Get password (same as pod name)
```
kubectl get pods -n argocd -l app.kubernetes.io/name=argocd-server -o name | cut -d'/' -f 2
```

Access Argo CD Port Forwarding¶
```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Access https://localhost:8080

Describe ConfigMap
```
kubectl describe configmap example-config
```


