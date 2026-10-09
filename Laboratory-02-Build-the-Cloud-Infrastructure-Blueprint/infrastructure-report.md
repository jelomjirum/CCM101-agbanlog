
# Cloud Infrastructure Assessment Report

## 1. Introduction

This report documents the investigation of a Linux server provided through the KillerCoda Playground. The purpose is to identify the server's operating system, computing resources, memory, storage, networking information, and mounted file systems.

## 2. Server Information

| Item | Actual Result |
|---|---|
| Operating System | [Copy from `/etc/os-release`] |
| Kernel Version | [Copy from `uname -r`] |
| CPU Model | [Copy from `lscpu`] |
| Number of CPU Cores | [Copy the CPU core count from `lscpu`] |
| Total RAM | [Copy total memory from `free -h`] |
| Disk Capacity | [Copy relevant disk information from `df -h`] |
| Hostname | [Copy from `hostname`] |
| IP Address | [Copy from `hostname -I`] |

## 3. Mounted File Systems

The `findmnt` command was used to inspect the file systems mounted in the Linux environment. The `df -h` command was also used to review disk space and usage.

[Add the relevant file system names and mount points from your terminal output.]

## 4. Analysis

The Linux environment provides the computing, memory, storage, and networking resources needed to run applications and perform server administration tasks. The available resources were investigated using Linux commands.

The actual capacity and configuration of the environment should be considered when planning a cloud deployment.

## 5. Evidence

- `screenshots/server-information.png`
- `screenshots/network-information.png`
- `screenshots/storage-information.png`

## 6. Conclusion

The investigation provided practical experience in examining a Linux server and collecting information that can help engineers plan cloud infrastructure. The findings in this report are based on the actual terminal output from the KillerCoda environment.
