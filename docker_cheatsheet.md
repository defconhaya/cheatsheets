**Basic Docker Commands:**

1. **Image Management:**
   - `docker pull <image_name>`: Pull an image from a registry (e.g., Docker Hub).
   - `docker build -t <image_name> <path_to_Dockerfile>`: Build an image from a Dockerfile.
   - `docker images` or `docker image ls`: List available images.
   - `docker rmi <image_id>`: Remove an image.
2. **Container Lifecycle:**
   - `docker run <image_name>`: Create and start a container from an image.
   - `docker ps`: List running containers.
   - `docker ps -a` or `docker container ls -a`: List all containers (including stopped ones).
   - `docker start <container_id>`: Start a stopped container.
   - `docker stop <container_id>`: Stop a running container.
   - `docker rm <container_id>`: Remove a container.
   - `docker logs <container_id>`: View container logs.
   - `docker exec -it <container_id> <command>`: Execute a command inside a running container.
3. **Container Networking:**
   - `docker network ls`: List Docker networks.
   - `docker network create <network_name>`: Create a new network.
   - `docker run --network <network_name> <image_name>`: Connect a container to a specific network.
4. **Volume Management:**
   - `docker volume ls`: List Docker volumes.
   - `docker volume create <volume_name>`: Create a new volume.
   - `docker run -v <volume_name>:<container_path> <image_name>`: Mount a volume to a container.
5. **Registry and Repository:**
   - `docker login`: Log in to a Docker registry (e.g., Docker Hub).
   - `docker push <image_name>`: Push an image to a registry.
   - `docker tag <image_name> <new_image_name>`: Tag an image with a new name.
6. **Docker Compose:**
   - `docker-compose up`: Start services defined in a `docker-compose.yml` file.
   - `docker-compose down`: Stop and remove containers defined in a `docker-compose.yml` file.
   - `docker-compose logs`: View logs of services.
7. **Cleanup:**
   - `docker system prune`: Remove all unused containers, networks, volumes, and images.
   - `docker system prune -a`: Remove all unused containers, networks, volumes, and images, including unused ones.
   
**Dockerfile Directives:**

- `FROM`: Specifies the base image.
- `RUN`: Executes commands during image build.
- `COPY` or `ADD`: Copies files into the image.
- `WORKDIR`: Sets the working directory for subsequent instructions.
- `EXPOSE`: Specifies which ports to expose.
- `CMD` or `ENTRYPOINT`: Defines the command to run when the container starts.

**Docker Compose Example:**

```yaml
version: '3'
services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
  app:
    build:
      context: ./myapp
    ports:
      - "3000:3000"
```
