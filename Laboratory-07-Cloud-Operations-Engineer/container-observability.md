# Container Observability Report

## 1. Introduction

Container observability involves monitoring application behavior, reviewing logs, and measuring resource usage to identify possible problems.

## 2. Nginx Container Deployment

**Command used:**

```bash
docker run -d --name client-website -p 8080:80 nginx
```

This command starts an Nginx container named `client-website` and maps port 8080 on the host to port 80 inside the container.

## 3. HTTP Request Testing

**Commands used:**

```bash
curl -i http://localhost:8080/
curl -i http://localhost:8080/index.html
curl -i "http://localhost:8080/?test=2"
curl -i http://localhost:8080/hidden-admin-page
```

The first three requests are intended to test accessible Nginx pages. The last request tests a nonexistent path and is expected to return HTTP 404 when the default Nginx configuration is used.

**Actual observations:**

- Successful request status codes: [ENTER ACTUAL RESULTS]
- Nonexistent path status code: [ENTER ACTUAL RESULT]

## 4. Container Log Monitoring

**Command used:**

```bash
docker logs client-website
```

**Actual log entry showing the test request:**

[PASTE AN ACTUAL RELEVANT LOG LINE HERE]

**Explanation:**

Container logs provide information about incoming requests, server responses, and errors. They help engineers investigate unexpected behavior and identify possible causes of application problems.

## 5. Container Resource Monitoring

**Command used:**

```bash
docker stats client-website
```

**Actual results:**

- CPU usage: [ENTER ACTUAL VALUE]
- Memory usage: [ENTER ACTUAL VALUE]
- Memory limit: [ENTER ACTUAL VALUE]

**Explanation:**

The `docker stats` command displays real-time resource usage for a running container. CPU and memory metrics help engineers identify resource consumption and potential performance issues.

## 6. Conclusion

Logs and resource metrics provide different but complementary information. Logs help explain what happened, while metrics show how resources are being used. Together, they support monitoring and troubleshooting.

**Note:** Replace the placeholders with results observed in your own terminal.
