# commands
```
kubectl api-versions | grep rbac
kubectl apply -f service-account.yaml
or
kubectl create namespace dev
kubectl -n dev create serviceaccount service-acc

TOKEN=$(kubectl -n dev create token service-acc)
echo $TOKEN
kubectl -n dev config set-credentials service-acc --token=$TOKEN
kubectl config current-context
cat ~/.kube/config |grep current-context
kubectl config set-context service-acc-context --cluster=minikube --user=service-acc (--cluster=default) (no namespace)
kubectl config use-context service-acc-context
kubectl -n dev config current-context
kubectl apply -f role-rolebinding.yaml (Error Forbidden)
kubectl -n dev run nginx --image=nginx:latest (Error Forbidden)
kubectl -n dev get pods (Error Forbidden)

kubectl config use-context minikube
kubectl apply -f role-rolebinding.yaml

kubectl -n dev config use-context service-acc-context
kubectl -n dev run nginx --image=nginx:latest (Success)
kubectl -n dev get pods (Success)
kubectl -n dev delete po nginx (Error)


kubectl config use-context minikube

kubectl -n dev get rolebinding -o yaml
kubectl dev delete role service-acc-role
kubectl delete rolebinding service-acc-role-binding
kubectl config use-context minikube (default)
kubectl config delete-context service-acc-context
kubectl config delete-user service-acc
kubectl config get-contexts
```