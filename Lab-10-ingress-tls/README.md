# commands
```
openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -keyout ingress-tls.key -out ingress-tls.crt
kubectl create namespace dev
kubectl create secret tls ingress-cert --namespace dev --key=ingress-tls.key --cert=ingress-tls.crt -o yaml
kubectl -n dev get secret
kubectl apply -f tls.yaml
kubectl -n dev delete secret ingress-cert
kubectl delete -f tls.yaml
```