# Rails Application with PostgreSQL on Kubernetes

This project demonstrates the deployment of a simple Ruby on Rails application with PostgreSQL on Kubernetes.

## Directory Structure

- **docker-related-files**: Docker-related files including Dockerfile, docker-compose.yml, entrypoint.sh, and init.sql.
- **kubernetes-manifests**: Kubernetes manifests for deploying the application and PostgreSQL on Kubernetes.
- **Readme.md**: This file.

## Docker Setup

### Dockerfile

The Dockerfile contains the configuration to build a Docker image for the Ruby on Rails application.

### docker-compose.yml

The docker-compose.yml file defines the services required to run the Ruby on Rails application and PostgreSQL database in separate containers.

## Kubernetes Setup

### Manifests

- **configmap.yml**: Kubernetes ConfigMap for storing application configuration.
- **namespace.yml**: Kubernetes Namespace for isolating the application.
- **postgres-statefullset.yml**: Kubernetes StatefulSet for deploying PostgreSQL.
- **ruby-app-deployment-service.yml**: Kubernetes Deployment and Service for deploying the Ruby on Rails application.
- **ruby-ingress.yml**: Kubernetes Ingress for exposing the application to external traffic.
- **secret.yml**: Kubernetes Secret for storing sensitive data.

## Deployment

1. Clone the Ruby on Rails application repository:

    ```bash
    git clone https://github.com/r-narayanan4/myapp.git
    ```

2. Navigate to the `3.Docker-Kubernetes/RailsApp-With-PostgreSQL-On-Kubernetes` directory.

3. Start the Docker containers using docker-compose:

    ```bash
    docker-compose up
    ```

4. Deploy the application on Kubernetes:

    ```bash
    kubectl apply -f kubernetes-manifests/
    ```

## Accessing the Application

Once deployed, you can access the Ruby on Rails application via the specified Ingress URL.

## Cleaning Up

To clean up resources, stop Docker containers and delete Kubernetes resources:

```bash
docker-compose down
kubectl delete -f kubernetes-manifests/
```