I created new main app for this: https://github.com/summis/devopswithkubernetes-main-app

Setup Kubernetes with similar commands as in material:
```
k3d delete
k3d create --publish 8081:80 --publish 8082:30080@k3d-k3s-default-worker-0 --workers 2
export KUBECONFIG="$(k3d get-kubeconfig --name='k3s-default')"
```
and start cluster with
```
kubectl apply \
-f https://github.com/summis/devopswithkubernetes-main-app/raw/master/manifests/deployment.yaml \
-f https://github.com/summis/devopswithkubernetes-main-app/raw/master/manifests/service.yaml \
-f https://github.com/summis/devopswithkubernetes-main-app/raw/master/manifests/ingress.yaml
```

After that hash can bee seen from http://localhost:8081/
Servers ouput can be checked with `kubectl logs -f <pod-name> main-app-server` where you can get pod name with `kubectl get pods`.


