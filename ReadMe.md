## Kubernetes Dashboard
- kubectl apply -f dashboard-adminuser.yaml
- kubectl apply -f admin-role-binding.yaml
- kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep admin-user | awk '{print $1}')
- kubectl proxy

## App Deploy and Access
- kubectl apply -f app-deployment.yaml
- kubectl port-forward deployment/client-deployment 8080:8080 -n default
 