# commands
```
kubectl apply -f ns.yaml
kubectl apply -f blue.yaml
kubectl apply -f green.yaml
kubectl apply -f service.yaml ( switch between env: blue/green. Test showing this is version 2. Increase/Decrease replicas)
kubectl apply -f ingress.yaml
kubectl get all -n prd
kubectl get ingress -n prd
```