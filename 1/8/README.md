Start with
```
kubectl apply \
-f https://raw.githubusercontent.com/summis/todo-app/v0.5/manifests/deployment.yaml \
-f https://raw.githubusercontent.com/summis/todo-app/v0.5/manifests/service.yaml \
-f https://raw.githubusercontent.com/summis/todo-app/v0.5/manifests/ingress.yaml
```
end with
```
kubectl delete \
-f https://raw.githubusercontent.com/summis/todo-app/v0.5/manifests/deployment.yaml \
-f https://raw.githubusercontent.com/summis/todo-app/v0.5/manifests/service.yaml \
-f https://raw.githubusercontent.com/summis/todo-app/v0.5/manifests/ingress.yaml
```
