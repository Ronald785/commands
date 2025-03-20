# Essential Docker Commands

This document contains a list of essential Docker commands that every developer should know to work efficiently with containers and images.

---

## 📌 1. Docker Information

### Check Docker Version

To check the installed Docker version:

```bash
docker --version
```

### List Docker Images

To list all images downloaded on your system:

```bash
docker images
```

### Search for an Image on Docker Hub

To search for an image on Docker Hub:

```bash
docker search <image-name>
```

---

## 🛠 2. Container Management

### List Running Containers

To list all running containers:

```bash
docker ps
```

To list all containers, including stopped ones:

```bash
docker ps -a
```

### Run a Container

To run a container from an image (example with the `nginx` image):

```bash
docker run -d -p 80:80 --name my-nginx nginx
```

**Explanation**:

-   `-d`: Run in "detached" mode (background).
-   `-p 80:80`: Maps port 80 of the container to port 80 of the host.
-   `--name`: Assigns a name to the container.

### Stop and Start a Container

To stop a running container:

```bash
docker stop <container-name-or-id>
```

To start a previously created but stopped container:

```bash
docker start <container-name-or-id>
```

### Remove a Container

To remove a stopped container:

```bash
docker rm <container-name-or-id>
```

To force-remove a running container:

```bash
docker rm -f <container-name-or-id>
```

---

## 🖼 3. Image Management

### Create a Docker Image

To create an image from a Dockerfile:

```bash
docker build -t image-name .
```

The `.` refers to the current directory where the Dockerfile is located.

### Remove an Image

To remove a Docker image:

```bash
docker rmi <image-name-or-id>
```

### Update Images

To update an image to the latest version:

```bash
docker pull <image-name>
```

---

## 🗄 4. Volume Management

### List Volumes

To list Docker volumes:

```bash
docker volume ls
```

### Create and Remove Volumes

To create a volume:

```bash
docker volume create <volume-name>
```

To remove a volume:

```bash
docker volume rm <volume-name>
```

---

## 📡 5. Docker Networking

### Create a Custom Docker Network

```bash
docker network create <network-name>
```

### List Existing Networks

```bash
docker network ls
```

---

## 📂 6. Logs and Diagnostics

### View Container Logs

To view logs of a running container:

```bash
docker logs <container-name-or-id>
```

### Inspect a Container or Image

To get details about a container or image:

```bash
docker inspect <container-name-or-id>
```

### Access a Running Container

To access the terminal of a running container (using `bash` or `sh`):

```bash
docker exec -it <container-name-or-id> bash
```

If the container does not have `bash`, you can try `sh`:

```bash
docker exec -it <container-name-or-id> sh
```

---

## 🧹 7. Cleanup and Optimization

### Clean Up Unused Containers, Images, and Volumes

To remove all stopped containers, unused images, and unused volumes:

```bash
docker system prune
```

---

## ⚙ 8. Docker Compose

### Run Docker Compose

Docker Compose is a tool for defining and running multi-container applications. To start the application defined in `docker-compose.yml`:

```bash
docker-compose up
```

To run in detached mode (background):

```bash
docker-compose up -d
```

To stop and remove containers, networks, and volumes created by `docker-compose`:

```bash
docker-compose down
```
