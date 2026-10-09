
# MinIO Deployment Documentation

## 1. Deployment Overview
MinIO was deployed as an S3-compatible object storage server using Docker in the KillerCoda Ubuntu Playground.

## 2. Docker Command

```bash
docker run -d \
  -p 9000:9000 \
  -p 9001:9001 \
  --name minio-server \
  -e "MINIO_ROOT_USER=cloudadmin" \
  -e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
  quay.io/minio/minio server /data --console-address ":9001"
```

## 3. Port Configuration
- **Port 9000:** MinIO S3 API.
- **Port 9001:** MinIO Web Console.

## 4. Environment Variables
The `-e` flag passes environment variables to the container.

- `MINIO_ROOT_USER` sets the MinIO root username.
- `MINIO_ROOT_PASSWORD` sets the MinIO root password.

These variables configure the login credentials used to access the MinIO service.

## 5. Bucket and Uploaded Object
- **Bucket name:** `client-photos`
- **Uploaded object:** [Write the actual filename of your uploaded file here.]

## 6. Verification
The container status was checked using:

```bash
docker ps
```

The MinIO Web Console was accessed through port 9001. The bucket and uploaded object were verified through the web interface.

## 7. Screenshots
- `screenshots/minio-deployed.png`
- `screenshots/minio-bucket-upload.png`

## 8. Notes
This is a learning environment for practicing Docker and object storage. The data directory is inside the container, so data may be lost if the container is removed. Persistent storage should be configured for data that must survive container removal.
