Now app can be started with
```
kubectl apply -f manifests/deployment.yaml; kubectl apply -f manifests/service.yml; kubectl apply -f manifests/ingress.yml
```
and stopped with
```
kubectl delete -f manifests/deployment.yaml; kubectl delete -f manifests/service.yml; kubectl delete -f manifests/ingress.yml
```
