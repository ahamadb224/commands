# Docker Cheat Sheet

## Table of Contents
1. [Basic Commands](#basic-commands)
2. [Container Management](#container-management)
3. [Image Management](#image-management)
4. [Network & Volume Management](#network--volume-management)
5. [Docker Compose](#docker-compose)
6. [Dockerfile Instructions](#dockerfile-instructions)

---

## Basic Commands

- Install Docker Engine: [Installation Guide](https://docs.docker.com/engine/install/)
- Install Docker Desktop: [Download Here](https://docs.docker.com/desktop/)
- Start Docker daemon:  
  ```sh
  docker -d
  ```
- Display Docker version:  
  ```sh
  docker version
  ```
- Show system-wide information:  
  ```sh
  docker info
  ```
- Get help with Docker commands:  
  ```sh
  docker --help
  ```

---

## Container Management

- Create and run a new container:  
  ```sh
  docker run <image>
  ```
- Run container with port mapping:  
  ```sh
  docker run -p <host_port>:<container_port> <image>
  ```
- Run container in the background:  
  ```sh
  docker run -d <image>
  ```
- Run container with volume mount:  
  ```sh
  docker run -v <host_dir>:<container_dir> <image>
  ```
- List running containers:  
  ```sh
  docker ps
  ```
- List all containers (including stopped ones):  
  ```sh
  docker ps -a
  ```
- Fetch container logs:  
  ```sh
  docker logs <container_name>
  ```
- Stop a running container:  
  ```sh
  docker stop <container_name>
  ```
- Start a stopped container:  
  ```sh
  docker start <container_name>
  ```
- Remove a container:  
  ```sh
  docker rm <container_name>
  ```
- Execute a command inside a running container:  
  ```sh
  docker exec -it <container_name> bash
  ```

---

## Image Management

- Build an image from a Dockerfile:  
  ```sh
  docker build -t <image_name> .
  ```
- Build an image without using cache:  
  ```sh
  docker build -t <image_name> . --no-cache
  ```
- List local images:  
  ```sh
  docker images
  ```
- Remove an image:  
  ```sh
  docker rmi <image_name>
  ```
- Remove all unused images:  
  ```sh
  docker image prune
  ```
- Login to Docker Hub:  
  ```sh
  docker login -u <username>
  ```
- Push an image to Docker Hub:  
  ```sh
  docker push <username>/<image_name>
  ```
- Pull an image from Docker Hub:  
  ```sh
  docker pull <image_name>
  ```

---

## Network & Volume Management

### Network Commands

- Create a new network:  
  ```sh
  docker network create <network_name>
  ```
- List networks:  
  ```sh
  docker network ls
  ```
- Connect a container to a network:  
  ```sh
  docker network connect <network_name> <container_name>
  ```
- Inspect network details:  
  ```sh
  docker network inspect <network_name>
  ```

### Volume Commands

- Create a volume:  
  ```sh
  docker volume create <volume_name>
  ```
- List volumes:  
  ```sh
  docker volume ls
  ```
- Remove a volume:  
  ```sh
  docker volume rm <volume_name>
  ```

---

## Docker Compose

- Start containers from `docker-compose.yml`:  
  ```sh
  docker-compose up
  ```
- Start containers in detached mode:  
  ```sh
  docker-compose up -d
  ```
- Stop running containers:  
  ```sh
  docker-compose stop
  ```
- Remove containers and networks:  
  ```sh
  docker-compose down
  ```
- View logs:  
  ```sh
  docker-compose logs
  ```
- Build or rebuild services:  
  ```sh
  docker-compose build
  ```

---

## Dockerfile Instructions

| Instruction | Description |
|-------------|------------|
| `FROM` | Set the base image |
| `RUN` | Execute a command during image build |
| `CMD` | Command to run when the container starts |
| `ENTRYPOINT` | Define the executable to run |
| `ENV` | Set environment variables |
| `EXPOSE` | Define the container's exposed ports |
| `COPY` | Copy files from host to container |
| `WORKDIR` | Set the working directory |
| `VOLUME` | Create a mount point |
| `USER` | Define which user to run the container as |

For a full reference, see the [Dockerfile documentation](https://docs.docker.com/engine/reference/builder/).

---

## Additional Resources

- Docker Official Documentation: [docs.docker.com](https://docs.docker.com/)
- Docker Hub: [hub.docker.com](https://hub.docker.com/)
- Docker Compose Guide: [docs.docker.com/compose](https://docs.docker.com/compose/)
