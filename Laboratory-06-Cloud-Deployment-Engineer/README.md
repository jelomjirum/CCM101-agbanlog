# Laboratory Activity 6: The Cloud Deployment Engineer

## 1. Mission Overview

This laboratory activity introduces multi-tier application architecture and Infrastructure as Code (IaC). Docker Compose is used to define and deploy a private cloud storage environment consisting of Nextcloud and MariaDB.

## 2. Objectives

- Explain the roles of the application tier and database tier.
- Create a `docker-compose.yml` configuration file.
- Deploy Nextcloud and MariaDB using Docker Compose.
- Access the Nextcloud setup page through port 8080.
- Shut down the application stack and document the process.

## 3. Tools Used

- KillerCoda Ubuntu Playground
- Docker
- Docker Compose
- Nextcloud
- MariaDB
- Nano text editor
- GitHub
- Web browser

## 4. Commands Executed

The following commands are used during the activity:

```bash
mkdir nextcloud-deployment
cd nextcloud-deployment
nano docker-compose.yml
docker compose up -d
docker compose ps
docker compose logs
docker compose down
```

If the environment uses the legacy Compose command, use `docker-compose` instead of `docker compose`.

## 5. Skills Learned

- Understanding two-tier architecture.
- Writing a YAML configuration file.
- Using environment variables in Docker Compose.
- Deploying multiple containers together.
- Accessing a web application through port mapping.
- Checking container status and logs.
- Documenting Infrastructure as Code.

## 6. Screenshots

The following evidence will be added after completing the activity:

- `screenshots/compose-deployment.png`
- `screenshots/nextcloud-web.png`
- `screenshots/compose-teardown.png`

## 7. Conclusion

This activity provides hands-on experience with Docker Compose and multi-container deployment. It demonstrates how a web application and database can operate as separate services within one application stack.
