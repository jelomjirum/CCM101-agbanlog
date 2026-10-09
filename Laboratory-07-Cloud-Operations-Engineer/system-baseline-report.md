# System Baseline Report

## 1. Introduction

System baseline monitoring helps determine the current resource usage of a Linux environment before and during container deployment.

## 2. Memory Monitoring

**Command used:**

```bash
free -h
```

**Actual results:**

- Total memory: [ENTER ACTUAL VALUE]
- Used memory: [ENTER ACTUAL VALUE]
- Available memory: [ENTER ACTUAL VALUE]

**Analysis:**

The `free -h` command displays total, used, free, and available memory. These values help determine whether the system has enough memory to run applications and containers.

## 3. Disk Monitoring

**Command used:**

```bash
df -h /
```

**Actual results:**

- Filesystem size: [ENTER ACTUAL VALUE]
- Used disk space: [ENTER ACTUAL VALUE]
- Available disk space: [ENTER ACTUAL VALUE]
- Usage percentage: [ENTER ACTUAL VALUE]

**Analysis:**

The `df -h /` command displays disk usage for the root filesystem. Monitoring disk space helps prevent problems caused by insufficient storage.

## 4. Process Monitoring

**Command used:**

```bash
top
```

The `top` command displays running processes and system resource usage, including CPU and memory consumption.

## 5. Conclusion

System baseline monitoring provides useful information about available memory, disk capacity, and running processes. These measurements help identify resource limitations and support troubleshooting.

**Note:** Replace all placeholders with the actual values obtained from the terminal.
