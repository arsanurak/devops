
### Deploy AWS Access Keys to Kubernetes

You will then need to create a secret in Kubernetes with the IAM user's credentials.
The secret can be created from the command line using `kubectl` as follows:

```shell script
kubectl create secret -n ns-ecr-renew-demo generic ecr-renew-cred-demo \
  --from-literal=REGION=[AWS_REGION] \
  --from-literal=ID=[AWS_KEY_ID] \
  --from-literal=SECRET=[AWS_SECRET]
```

```shell script
kubectl create secret -n ns-ecr-renew-demo generic ecr-renew-cred-demo \
  --from-literal=REGION=ap-southeast-1 \
  --from-literal=ID=AKIAJPARFOQIKG2JAEMQ \
  --from-literal=SECRET=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
```

```shell script
kubectl apply -f 4\ k8s\ ECR\ manual\ setup\ /service-account.yml -n ns-ecr-renew-demo
```

```shell script
kubectl apply -f 4\ k8s\ ECR\ manual\ setup\ /deploy.yml -n ns-ecr-renew-demo
```

```shell script
kubectl create job --from=cronjob/ecr-renew-demo ecr-renew-demo-manual-1
```

```shell script
kubectl apply -f 4\ k8s\ ECR\ manual\ setup\ /pod.yml
```