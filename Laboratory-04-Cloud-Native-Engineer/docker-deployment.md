# Docker Deployment and Container Lifecycle

## 1. Objective

The objective of this activity is to download the official Nginx image, run a containerized web server, verify its HTTP response, and manage the container lifecycle using Docker commands.

## 2. Docker Environment Verification

### Command 1: Check Docker Version

```bash
docker --version
```

**Explanation:** Displays the installed Docker client version.

### Command 2: Inspect Docker Environment

```bash
docker info
```

**Explanation:** Displays information about the Docker environment and daemon when the client can connect successfully.

## 3. Deploy Nginx

### Command 3: Download the Nginx Image

```bash
docker pull nginx
```

**Explanation:** Downloads the Nginx image from the configured Docker registry.

### Command 4: Run the Nginx Container

```bash
docker run -d --name nginx-lab -p 8080:80 nginx
```

**Explanation:** Creates and runs a container in the background and maps host port 8080 to container port 80.

### Command 5: Verify the Running Container

```bash
docker ps
```

**Explanation:** Lists running containers and displays their status and port mappings.

### Command 6: Test the Web Server

```bash
curl http://localhost:8080
```

**Explanation:** Sends an HTTP request to the mapped local port and displays the returned HTML if the web server responds successfully.

## 4. Container Lifecycle Management

### Command 7: List Running Containers

```bash
docker ps
```

**Explanation:** Lists containers that are currently running.

### Command 8: Stop the Container

```bash
docker stop nginx-lab
```

**Explanation:** Stops the running container named `nginx-lab`.

### Command 9: Verify the Stopped Container

```bash
docker ps -a
```

**Explanation:** Lists all containers, including stopped containers, so the status can be verified.

### Command 10: Remove the Container

```bash
docker rm nginx-lab
```

**Explanation:** Removes the stopped container from Docker.

### Command 11: Confirm Removal

```bash
docker ps -a
```

**Explanation:** Confirms that the removed container no longer appears in the container list.

## 5. Screenshot Evidence

- `screenshots/docker-version.png`
- `screenshots/nginx-running.png`
- `screenshots/container-lifecycle.png`

## 6. Conclusion

This activity demonstrates how Docker can package and run a web server without requiring a separate guest operating system for the application. The lifecycle commands provide basic skills for inspecting, stopping, and removing containers.
