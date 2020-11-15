# Udacity DevOps Capstone Project

- [Udacity DevOps Capstone Project](#udacity-devops-capstone-project)
  - [Overview](#overview)
  - [Project Contents](#project-contents)
  - [CloudFormation Commands](#cloudformation-commands)
  - [Kubernetes Commands](#kubernetes-commands)
  - [Docker Commands](#docker-commands)

## Overview

project description 

## Project Contents

* content 1
* content 2
* content 2

## CloudFormation Commands

Create new stack to provision EKS cluster and worker nodes

```
./scripts/create.sh capstone-eks-stack ./templates/eks-cluster.yml ./templates/eks-cluster-parameters.json
```

Delete the stack

```
./scripts/delete.sh capstone-eks-stack 
```

## Kubernetes Commands

Update kubeconfig with the newly created cluster

```
aws eks update-kubeconfig --name UdacityProject-EKS --region us-west-2
```

create a new deployment from docker image

```
kubectl create deployment udacity-project --image=faalsh/udacity-project:1.0
```

get the pods and wait for running state

```
kubectl get pods
```

test the pod locally using port forward

```
kubectl port-forward deployment/udacity-project 8000:80
```

expose the service

```
kubectl expose deployment udacity-project --type=LoadBalancer --name=udacity-lb --port=8080 --target-port=80
```

get service details

```
kubectl describe service/udacity-lb
```

## Docker Commands

Build docker image locally

```
docker build -t books-app .
```

Run docker image locally

```
docker run --name books-app -p 8080:8080 books-app
```

Push docker image to registry

```
docker login --username=<username>

docker tag books-apps <user>/books-apps

docker push <user>/books-apps

```