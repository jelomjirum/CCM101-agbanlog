# Multi-Tier Architecture

## 1. What Is a Two-Tier Architecture?

A two-tier architecture is an application design that separates an application into two main parts: the web/application tier and the database tier. These tiers communicate with each other to provide services to users.

## 2. Web/Application Tier

The web/application tier handles user requests and provides the web interface. In this activity, Nextcloud runs in a Docker container and allows users to access a private cloud storage service through a web browser.

## 3. Database Tier

The database tier stores important application data, such as user accounts, configuration information, and file metadata. In this activity, MariaDB runs in a separate Docker container and serves as the database for Nextcloud.

## 4. Why Separate Them?

Separating the web application and database into different containers makes the system easier to manage, update, and troubleshoot. Each container has its own responsibility, and the application can communicate with the database through the configured container network. This design also makes it easier to scale or replace one component without rebuilding the entire application.

## 5. Architecture Summary

- **Application:** Nextcloud
- **Database:** MariaDB
- **Application port:** 8080 on the host, mapped to port 80 in the container
- **Database hostname:** `database`
- **Deployment tool:** Docker Compose
