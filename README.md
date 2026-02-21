# Local-Minikube-Kubernetes

Created this repo to note down my learning of kubernetes using minikube in a virtual machine

Currently using Minikube


### Requirments

- Docker
- Minikube
- kubernetes cluter or can be done locally in a VPS

> Recomended to install podman so that you can see all your kubernetes pods, services etc


> Before starting, make sure to learn docker basics
>
> Also create a basic docker image of a basic project for learing and seeing kubernetes in action! In my case i dockerized a astro application


### Initial steps and some commands


``` bash

minikube start #Start the kubernetes

kubectl get pods # To check if any pods exist

```

In kubernetes you write all your deployments in YAML Files

We first will create a smalled pod in kubernetes 

>Create a pods.yaml file 

``` bash
kubectl apply -f pods.yaml 
kubectl get pods

```
