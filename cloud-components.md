
# Cloud Infrastructure Components

## 1. Compute Resources

**Purpose:** Compute resources process instructions and run applications. They include CPU resources, virtual machines, and containers.

**Importance in Cloud Computing:** Compute resources allow organizations to host websites, applications, databases, and other workloads. Cloud platforms let organizations adjust computing capacity according to demand.

**Relation to KillerCoda:** The Linux environment provides CPU resources that can be inspected using the `lscpu` command. These resources allow the server to execute Linux commands and run supported applications.

## 2. Storage Resources

**Purpose:** Storage resources hold operating system files, application files, documents, and other data.

**Importance in Cloud Computing:** Reliable storage allows applications to save and retrieve information. Cloud storage can provide scalable capacity, backup options, and data durability depending on the service and configuration.

**Relation to KillerCoda:** The Linux environment has mounted file systems and available disk space. The `df -h` and `findmnt` commands help identify disk usage and mounted file systems.

## 3. Networking Resources

**Purpose:** Networking resources connect computers, servers, applications, and users so they can communicate.

**Importance in Cloud Computing:** Networking enables access to cloud applications, communication between services, and controlled connectivity to external systems.

**Relation to KillerCoda:** The server has network interfaces and may have one or more IP addresses. The `hostname -I` and `ip addr` commands can be used to inspect its network addressing.

## 4. Operating System

**Purpose:** An operating system manages hardware resources and provides the environment where applications and commands run.

**Importance in Cloud Computing:** The operating system supports application execution, resource management, security configuration, and system administration.

**Relation to KillerCoda:** The provided server runs Linux. The `cat /etc/os-release` and `uname -r` commands identify the operating system information and kernel version.

## Conclusion

Compute, storage, networking, and the operating system work together to support cloud workloads. Understanding these components helps engineers assess available resources, identify requirements, and plan a suitable cloud infrastructure.
