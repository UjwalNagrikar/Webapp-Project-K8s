# Kubernetes Project: Deploying a Website on Kubernetes

This is my first project on Kubernetes where I deployed a simple website using HTML, CSS, and JavaScript. The project uses Docker to containerize the application and Kubernetes to manage the deployment.

## Project Description

This project showcases how to deploy a website on a Kubernetes cluster. The steps involve building a Docker image, pushing it to a container registry, and using Kubernetes resources like Deployments and Services to manage and expose the application.

## Steps to Deploy the Website

### 1. Build the Docker Image

Build the Docker image for the website.
```bash
docker build -t ujwalnagrikar/ujwal-dev:latest .
```

### 2. Verify the Docker Image

Check the Docker images to confirm the build.
```bash
docker images
```

### 3. Log in to Docker Hub

Authenticate with Docker Hub.
```bash
docker login
```

### 4. Push the Docker Image to Docker Hub

Push the built image to the Docker Hub repository.
```bash
docker push ujwalnagrikar/ujwal-dev:latest
```

### 5. Create a Kubernetes Deployment

Create a Kubernetes Deployment using the Docker image.
```bash
kubectl create deployment my-pro --image=ujwalnagrikar/ujwal-dev:latest
```

### 6. Verify the Deployment

List all deployments in the cluster.
```bash
kubectl get deployments
```

List the pods created by the deployment.
```bash
kubectl get pods
```

Check the status of a specific pod.
```bash
kubectl get pods my-pro-cf754d849-5k47m
```

### 7. Expose the Deployment as a Service

Expose the deployment as a LoadBalancer service on port 8080.
```bash
kubectl expose deployment my-pro --type=LoadBalancer --port=8080
```

### 8. Verify the Service

List all services in the cluster.
```bash
kubectl get services
```

### 9. Access the Application

Use Minikube to open the service in the default browser.
```bash
minikube service my-pro
```

## Screenshots

Below are screenshots demonstrating the steps and the deployed website:

1. **Deployed Website:** The website successfully running on the Kubernetes cluster.

2. **Docker Commands:** Building, pushing the Docker image, and Kubernetes deployment commands executed.

3. **Kubernetes Pods and Services:** Output of commands verifying deployments and services.

## Tools and Technologies Used

- **Docker**: For containerizing the application.
- **Kubernetes**: For orchestrating the containers.
- **Minikube**: For running the Kubernetes cluster locally.
- **HTML, CSS, JS**: For building the website.
