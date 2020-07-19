Set up kubernetes with commands from material
```console
k3d create --publish 8081:80 --publish 8082:30080@k3d-k3s-default-worker-0 --workers 2
export KUBECONFIG="$(k3d get-kubeconfig --name='k3s-default')"
```
and then make folder in `k3d-k3s-default-worker-0` container and set permission such that it is available for pong app to write (should avoid setting 777 permissions but this is quick and dirty)
```console
docker exec k3d-k3s-default-worker-0 mkdir /tmp/kube
docker exec k3d-k3s-default-worker-0 chmod -R 777 /tmp/kube
```

Next start apps with
```
kubectl apply \
-f https://raw.githubusercontent.com/summis/devopswithkubernetes-main-app/master/manifests/deployment-persistent.yaml \
-f https://raw.githubusercontent.com/summis/devopswithkubernetes-main-app/master/manifests/service.yaml \
-f https://raw.githubusercontent.com/summis/devopswithkubernetes-main-app/master/manifests/ingress.yaml \
-f https://raw.githubusercontent.com/summis/devopswithkubernetes-main-app/master/manifests/persistentvolume.yaml \
-f https://raw.githubusercontent.com/summis/devopswithkubernetes-main-app/master/manifests/persistentvolumeclaim.yaml
```
and
```
kubectl apply \
-f https://raw.githubusercontent.com/summis/pong-app/master/manifests/deployment-persistent.yaml \
-f https://raw.githubusercontent.com/summis/pong-app/master/manifests/service.yaml \
-f https://raw.githubusercontent.com/summis/pong-app/master/manifests/ingress.yaml
```
