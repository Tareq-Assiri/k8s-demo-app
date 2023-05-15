k8s-demo-app
============

This repository contains instructions and configuration files for deploying a Kubernetes cluster using MongoDB and a Docker container.

Prerequisites
-------------

Before deploying the Kubernetes cluster, you will need to have the following software installed:

- Kubernetes
- Docker
- kubectl

You will also need to have an active Kubernetes cluster to deploy the application to.

Getting Started
---------------

To get started,clone this repository to your local machine using the following command:

```
git clone https://github.com/Tareq-Assiri/k8s-demo-app

```
pull this image to your local machine using the following command:

```
docker pull /nanajanashia/k8s-demo-app

```

Next, navigate to the root directory of the repository and deploy the it directly to your Kubernetes cluster.

Deploying to Kubernetes
-----------------------

To deploy the application to your Kubernetes cluster, navigate to the `k8s` directory and run the following command:

```
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo.yaml
kubectl apply -f mongo-config.yaml
kubectl apply -f webapp.yaml

```

This will create a MongoDB deployment with 3 replicas and a webapp deployment with 5 replicas for the k8s-demo-app container.

Accessing the Application
-------------------------

To access the application, you will need to access the NodePort service for the k8s-demo-app container by navigating to `http://<node-ip>:<node-port>` in your web browser.

Cleaning Up
-----------

To delete the MongoDB and k8s-demo-app deployments, run the following command:

```
kubectl delete deployment mongo-deployment webapp-deployment

```

To delete the NodePort service, run the following command:

```
kubectl delete service webapp-service

```

Conclusion
----------
this is just an example on how to deploy a Kubernetes cluster using a docker image

