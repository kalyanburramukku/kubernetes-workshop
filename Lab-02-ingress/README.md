# commands
```
kubectl get ingress -n qa
minikube addons list
minikube addons enable ingress
update $(minikube ip) demo.example.com in /etc/hosts
eg: 192.168.49.2 demo.example.com
kubectl apply -f ingress.yaml
kubectl get all -n qa
minikube dashboard
sudo sed -i '/com$/d' /etc/hosts
kubectl delete -f ingress.yaml
```