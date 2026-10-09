# Laboratory Activity 4: The Cloud-Native Engineer

## 1. Mission Overview

This laboratory activity explores the differences between traditional virtual machines and containers. It uses Docker in a KillerCoda Linux environment to deploy an Nginx web server and demonstrate basic container lifecycle management.

## 2. Objectives

- Differentiate virtual machines from containers.
- Verify the Docker environment.
- Download and run an Nginx container.
- Test the web server using an HTTP request.
- Stop and remove a container.
- Document technical procedures using Markdown and GitHub.

## 3. Docker Commands Executed

| Command | Purpose |
|---|---|
| `docker --version` | Check the Docker client version |
| `docker info` | Inspect the Docker environment |
| `docker pull nginx` | Download the Nginx image |
| `docker run -d --name nginx-lab -p 8080:80 nginx` | Run Nginx in the background and map its port |
| `docker ps` | List running containers |
| `curl http://localhost:8080` | Test the local web server |
| `docker logs nginx-lab` | Inspect container logs when troubleshooting |
| `docker stop nginx-lab` | Stop the container |
| `docker ps -a` | List running and stopped containers |
| `docker rm nginx-lab` | Remove the stopped container |

## 4. Skills Learned

This activity provides practice in Docker image management, container deployment, port mapping, HTTP testing, container lifecycle management, Linux terminal operations, and technical documentation.

## 5. Challenges Encountered

During the activity, I needed to verify that Docker was available and that the Nginx container could start successfully. I used the Docker status and container listing commands to check the environment and troubleshoot potential issues. I documented the actual results and any additional problems encountered during the laboratory.

## 6. Deliverables

- `virtualization-vs-containers.md`
- `docker-deployment.md`
- `reflection.md`
- `screenshots/docker-version.png`
- `screenshots/nginx-running.png`
- `screenshots/container-lifecycle.png`

## 7. Conclusion

The activity demonstrates how Docker can simplify application deployment by using containers. It also develops basic skills for checking Docker, running an Nginx web server, testing port connectivity, and managing the container lifecycle.
