## How to setup K8S Dev

### Install k3s on dev server

on Dev server install alpine 3.xx

```
echo "k3s01" > /etc/hostname

apk add curl
curl -sfL https://get.k3s.io | sh -
k3s kubectl get node

```

### contexts

```
#get the current context
kubectl config current-context

#get and set contexts
kubectl config get-contexts
kubectl config use-context

```

## GET commands
```
kubectl get <resource>

#examples
kubectl get pods
kubectl get deployments
kubectl get services
kubectl get configmaps
kubectl get secrets
kubectl get ingress

```

## Namespaces

```
kubectl get namespaces
kubectl create namespace test
kubectl get pods -n test

```

## Describe command

Used to troubleshoot states and statuses of objects

```
kubectl describe <resource> <name>
```

## Version

```
kubectl version
```

## how to get kube config

```
cat /etc/rancher/k3s/k3s.yaml
# create local and copy to 
# ~/.kube/config
```
## how to get node token

```
cat /var/lib/rancher/k3s/server/node-token
```

## How to  join a worker node

```
curl -sfL https://get.k3s.io | K3S_URL=https://192.168.10.70:6443 K3S_TOKEN=K10f9985b3209e19ce889b68312296a6ca70c1b545862e95ae96150cbe80a56fa4a::server:5936c5ddff8e3c691fb92705701f28d8 sh -
```


## How to  join a worker node

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml
```
Access

http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/login



