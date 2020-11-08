## Kubernetes Dashboard
- kubectl apply -f dashboard-adminuser.yaml
- kubectl apply -f admin-role-binding.yaml
- kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep admin-user | awk '{print $1}')
- kubectl proxy

## App Deploy and Access
- kubectl apply -f app-deployment.yaml
- kubectl port-forward deployment/client-deployment 8080:8080 -n default

## Helm
- helm create myapp
- helm install myapp myapp/ --values myapp/values.yaml
- helm del myapp -n default
- kubectl port-forward deployment/myapp 8080:8080 -n default
- helm upgrade myapp myapp/ --values myapp/values.yaml

## Kubernetes General
- kubectl delete --all deployments
- kubectl delete --all namespaces

## Creating a Cluster IP
kubectl run --generator=run-pod/v1 tmp-shell --rm -it --image bretfisher/netshoot -- bash

## Creating a Node Port
kubectl expose deployment/httpenv --port 8888 --name httpenv-np --type NodePort
