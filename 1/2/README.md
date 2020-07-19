My todo app: https://github.com/summis/todo-app. I used branch `v01` in this exercise.

I created docker image with
```console
$ docker build -t summila/todo-app .
$ docker push summila/todo-app:v0.1
```
and deployed it to Kubernetes cluster with
```console
$ kubectl create deployment todo-app --image=summila/todo-app:v0.1
```
