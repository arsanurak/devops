## How to deploy

```
kubectl apply -f ./3\ k8s\ Deployment/deployment.yaml 
```
## How check deploy

```
kubectl get deploy
kubectl describe deploy example-deploy
watch kubectl get deploy
kubectl describe pods example-deploy-64995d64d4-h5w4x
kubectl logs pods example-deploy-64995d64d4-h5w4x
```
