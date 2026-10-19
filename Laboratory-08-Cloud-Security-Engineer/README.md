
# Laboratory 08: Cloud Security and Firewall Management

## Mission Overview

This laboratory demonstrates how to secure a Linux-based cloud environment by implementing firewall protection and managing network access. The activity involves running an Nginx web server inside a Docker container and using the Uncomplicated Firewall (UFW) to manage incoming and outgoing connections. Security settings were applied to block unauthorized traffic while allowing SSH access and web application connections through port 8080.

## Objectives

The main goals of this laboratory are:

1. Learn the importance of securing cloud-based servers.
2. Understand how the Principle of Least Privilege protects system resources.
3. Recognize possible network entry points that may become security risks.
4. Launch a containerized Nginx web server using Docker.
5. Apply firewall policies that restrict unwanted incoming traffic.
6. Maintain remote server access through SSH on port 22.
7. Configure port 8080 for web application communication.
8. Examine firewall configurations and verify application availability.
9. Record laboratory procedures and security practices using Markdown.

## Commands Executed

### 1. Preparing and Running the Web Application

The following commands check the Docker installation, create an Nginx container, and verify that the application is running.

```bash
docker --version
docker run -d --name secure-web-app -p 8080:80 nginx:alpine
docker ps
curl http://localhost:8080
```

### 2. Setting Up Firewall Protection

UFW was used to establish network access restrictions and configure the server's default connection policies.

```bash
sudo ufw status
sudo ufw allow ssh
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo ufw status verbose
```

### 3. Managing Allowed Ports and Testing Connectivity

These commands configure access to the web application and inspect the current firewall rules.

```bash
sudo ufw allow 8080/tcp
sudo ufw status numbered
curl http://localhost:8080
curl -I http://localhost:8080
```

## Skills Learned

After performing this laboratory activity, I gained knowledge and practical experience in the following areas:

- **Cloud Infrastructure Protection:** Understanding basic techniques for protecting servers against unauthorized network access.
- **Access Control:** Applying the Principle of Least Privilege to limit unnecessary permissions and connections.
- **Network Security:** Identifying exposed services and reducing potential attack points.
- **Firewall Administration:** Managing Linux firewall rules using UFW commands.
- **Traffic Filtering:** Understanding how Default Deny policies restrict unapproved incoming connections.
- **Port Configuration:** Managing SSH and web application ports for authorized network communication.
- **Docker Management:** Deploying and checking a containerized Nginx web server.
- **Application Testing:** Using curl commands to check local web server responses.
- **Technical Documentation:** Organizing security procedures and commands in Markdown for GitHub.

## Conclusion

Laboratory 08 provided practical experience in applying fundamental cloud security practices. Through Docker and UFW, I learned how to deploy a web application while configuring network restrictions to protect the server. The activity also demonstrated the importance of limiting unnecessary access, checking active services, and regularly reviewing firewall settings to maintain a more secure cloud environment.
