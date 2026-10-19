
# Linux Firewall Setup and Security Management

## Laboratory 08 - Cloud Security Engineer

### Introduction

This laboratory demonstrates the process of protecting an Ubuntu server by setting up firewall rules through the Uncomplicated Firewall (UFW). The main purpose is to control network connections, prevent unwanted access, and ensure that important services remain accessible. SSH is used for remote administration, while TCP port 8080 supports the Nginx application running through Docker.

## Firewall Setup Procedure

### 1. Permit Remote Server Access

Before activating firewall protection, SSH connections must be allowed to prevent interruptions during remote administration.

**Command:**

```bash
sudo ufw allow ssh
```

This instruction creates a firewall rule that permits SSH communication through its standard port, 22.

### 2. Establish Network Traffic Restrictions

A secure firewall configuration should reject incoming requests unless permission is specifically granted.

**Commands:**

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

**Explanation:**

- `default deny incoming` prevents unauthorized incoming network connections.
- `default allow outgoing` permits the server to establish connections to external services.

These settings establish a basic security policy that limits unnecessary network exposure.

### 3. Activate Firewall Protection

After preparing the necessary access rules, the firewall can be enabled.

**Command:**

```bash
sudo ufw enable
```

This activates UFW and begins enforcing the configured firewall rules.

### 4. Inspect Current Firewall Settings

The administrator should check whether the firewall is active and review its existing configuration.

**Command:**

```bash
sudo ufw status verbose
```

This displays detailed firewall information, including default traffic policies and permitted ports.

### 5. Configure Application Network Access

The Nginx web application uses port 8080 on the host, so a firewall rule must be created to permit the required traffic.

**Command:**

```bash
sudo ufw allow 8080/tcp
```

This rule permits incoming TCP connections through port 8080 under UFW's filtering rules.

### 6. Review Configured Firewall Rules

To confirm that the necessary access rules are present, display the firewall configuration in numbered format.

**Command:**

```bash
sudo ufw status numbered
```

The numbered output makes firewall rules easier to identify when reviewing or modifying the configuration.

### 7. Check Web Server Availability

After completing the firewall configuration, test whether the Nginx application responds correctly.

**Command:**

```bash
curl http://localhost:8080
```

A successful request should return the web server's response, indicating that the application is accessible from the local machine.

## Safety Precautions

When configuring UFW on a remotely accessed server, it is important to permit SSH before enabling the firewall. Otherwise, the administrator might lose access to the system.

Docker containers also require special attention because published container ports may bypass some UFW restrictions. Additional network filtering may be necessary to ensure that Docker traffic follows the intended security policy.

## Recommended Security Measures

1. Maintain firewall rules that allow only essential services.
2. Limit remote server access to authorized administrators.
3. Remove firewall exceptions that are no longer needed.
4. Keep the Ubuntu operating system and Docker software updated.
5. Inspect exposed container ports to identify possible vulnerabilities.
6. Avoid making internal database services publicly accessible.
7. Perform regular security checks to maintain proper network protection.

## Summary

The firewall configuration activity provided practical knowledge of network access management using UFW. By applying restrictive incoming traffic policies and allowing necessary services, the server can reduce potential security risks. The laboratory also demonstrated the importance of verifying firewall rules, testing web application connectivity, and maintaining security controls for Docker-based applications.

