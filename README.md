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
Here we have created a sucessfully deployed our first kubernetes pods, we can check this but running the get pods commands and can also see in podman too

In the next step we try to create a deployment with replicas

> create deps.yaml

``` bash
kubectl apply -f deps.yaml
kubectl get deployments
kubectl get pods                          # see 2 pods running
kubectl rollout status deployment/my-app

# Scale on the fly
kubectl scale deployment my-app --replicas=4

# Update the image (triggers rolling update)
kubectl set image deployment/my-app my-app=tidersky/ass:li

# Rollback if something breaks
kubectl rollout undo deployment/my-app
kubectl rollout history deployment/my-app

```

Scaling can be done with scale command and after that we can run get pods command and see we will be having multiple pods

### service

Now that we have everything running we need to expose the pods so that we can access them through our browser


