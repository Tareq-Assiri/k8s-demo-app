# k8s-demo-app

This repository contains instructions and configuration files for deploying a Kubernetes cluster using MongoDB and a Docker container.

## Prerequisites

Before deploying the Kubernetes cluster, you will need to have the following software installed:

- Kubernetes
- Docker
- kubectl

You will also need to have an active Kubernetes cluster to deploy the application to.

## Getting Started

To get started, clone this repository to your local machine using the following command:

```
git clone https://github.com/nanajanashia/k8s-demo-app.git
```

Next, navigate to the root directory of the repository and run the following command to build the Docker container:

```
docker build -t k8s-demo-app .
```

Once the container has been built, you can push it to a Docker registry or deploy it directly to your Kubernetes cluster.

## Deploying to Kubernetes

To deploy the application to your Kubernetes cluster, navigate to the `k8s` directory and run the following command:

```
kubectl apply -f mongo-deployment.yaml
kubectl apply -f app-deployment.yaml
```

This will create a MongoDB deployment and a deployment for the k8s-demo-app container.

## Accessing the Application

To access the application, you will need to expose the service as a NodePort. To do this, run the following command:

```
kubectl expose deployment k8s-demo-app --type=NodePort --port=8080
```

This will create a NodePort service for the k8s-demo-app container. You can access the application by navigating to `http://<node-ip>:<node-port>` in your web browser.

## Cleaning Up

To delete the MongoDB and k8s-demo-app deployments, run the following command:

```
kubectl delete deployment mongo k8s-demo-app
```

To delete the NodePort service, run the following command:

```
kubectl delete service k8s-demo-app
```

## Conclusion

This repository provides a simple example of how to deploy a Kubernetes cluster using MongoDB and a Docker container. You can modify the configuration files to suit your own requirements, and use this as a starting point for your own Kubernetes projects.

