Setup Kubernetes with similar commands as in material:
```
k3d delete
k3d create --publish 8081:80 --publish 8082:30080@k3d-k3s-default-worker-0 --workers 2
export KUBECONFIG="$(k3d get-kubeconfig --name='k3s-default')"
```
and start cluster with
```
kubectl apply \
-f https://raw.githubusercontent.com/summis/pong-app/master/manifests/deployment.yaml \
-f https://raw.githubusercontent.com/summis/pong-app/master/manifests/service.yaml \
-f https://raw.githubusercontent.com/summis/pong-app/master/manifests/ingress.yaml
```
