# Docker Technical Documentation

## Introduction

Docker is a platform for developing, shipping, and running applications in containers. It provides a consistent environment across different stages of development, from a developer's local machine to production servers. This consistency significantly reduces the "it works on my machine" problem and streamlines the development pipeline.

## Key Concepts

### Containers

Containers are lightweight, standalone, executable packages that include everything needed to run a piece of software, including the code, runtime, system tools, libraries, and settings. They are isolated from one another and bundle their own software, libraries, and configuration files; they can communicate with each other through well-defined channels.

Key benefits of containers include:
- Consistency across development, testing, and production environments
- Isolation and segmentation of applications
- Portability across different platforms and clouds

### Images

A Docker image is a lightweight, standalone, and executable package that includes everything needed to run a piece of software. It contains all the necessary code, runtime, system tools, libraries, and settings. Images are used to create containers, and are composed of layers of other images, allowing for efficient storage and transfer.

### Dockerfile

A Dockerfile is a text file that contains instructions for building a Docker image. It specifies the base image, environment variables, dependencies, and commands needed to set up the application. Each instruction in a Dockerfile creates a new layer in the image, allowing for caching and efficient rebuilds.

Example of a simple Dockerfile:

```
FROM ubuntu:20.04
RUN apt-get update && apt-get install -y python3
COPY ./app /app
WORKDIR /app
CMD ["python3", "app.py"]
```

### Docker Hub

Docker Hub is a cloud-based registry service that allows you to link to code repositories, build images, and test them. It provides a centralized resource for container image discovery, distribution, and change management. Users can push their custom images to Docker Hub or use official images maintained by software vendors.

## Docker Architecture

Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing Docker containers. The client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon.

1. Docker daemon (dockerd): Listens for Docker API requests and manages Docker objects.
2. Docker client: The primary way users interact with Docker, sending commands to dockerd.
3. Docker registries: Stores Docker images. Docker Hub is a public registry anyone can use.

## Basic Commands

1. `docker build -t my-image .`: Build an image from a Dockerfile in the current directory and tag it as "my-image".
2. `docker run -d -p 80:80 my-image`: Run a container from the "my-image" image, mapping port 80 of the container to port 80 on the host machine.
3. `docker pull ubuntu:20.04`: Pull the Ubuntu 20.04 image from Docker Hub.
4. `docker push myusername/my-image`: Push the "my-image" image to Docker Hub under your username.
5. `docker ps`: List running containers.
6. `docker images`: List available images on your local machine.
7. `docker stop container_id`: Stop a running container.
8. `docker rm container_id`: Remove a stopped container.

## Networking in Docker

Docker creates a default bridge network for containers to communicate. You can also create custom networks:

1. `docker network create my-network`: Create a custom network.
2. `docker run --network my-network my-image`: Run a container connected to the custom network.

Containers on the same network can communicate using their names as hostnames.

## Volumes and Data Persistence

Docker provides volumes for persisting data and sharing data between containers:

1. `docker volume create my-volume`: Create a named volume.
2. `docker run -v my-volume:/app/data my-image`: Mount the volume in a container.

## Best Practices

1. Use official base images: They are maintained and regularly updated with security patches.
2. Minimize the number of layers: Combine commands to reduce the number of layers and image size.
3. Use multi-stage builds: Create smaller final images by using one stage to build and another for the runtime.
4. Avoid running containers as root: Use the USER instruction to specify a non-root user for security.
5. Use environment variables for configuration: This allows for easier configuration changes without rebuilding the image.
6. Keep images small: Only include what's necessary for your application to run.
7. Use .dockerignore: Exclude files not relevant to the build, speeding up the build process.

## Docker Compose

Docker Compose is a tool for defining and running multi-container Docker applications. It uses YAML files to configure application services and performs the creation and start-up of all the containers with a single command.

Example docker-compose.yml:

```yaml
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
```

To run this multi-container application: `docker-compose up`

