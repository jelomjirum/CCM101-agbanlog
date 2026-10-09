# Mission Reflection: The Cloud Data Engineer

This laboratory activity helped me understand the importance of cloud storage and how object storage works. Block storage stores data in blocks and is commonly used for virtual machine disks and databases. Although it is useful for these purposes, object storage is more suitable for applications that need to store millions of photos. Each photo can be stored as an object with its own metadata and identifier. This makes object storage a practical option for organizing and retrieving large collections of images.

Docker made deploying MinIO easier because I could start the storage server using a single command instead of manually installing and configuring every component. The command also allowed me to map ports and set environment variables for the login credentials. I learned that port 9001 is used to access the MinIO Web Console, while port 9000 is used for the S3 API.

A bucket is a container used to organize objects in an object storage system. In this activity, the bucket named `client-photos` was intended to store the sample image or text file uploaded through the web interface. Creating the bucket and uploading a file helped me understand how a storage administrator manages objects.

Large enterprise companies can reduce the risk of data loss through replication, multiple storage devices, backups, monitoring, and recovery plans. They may also distribute data across different servers or locations. These methods help maintain availability when hardware fails, although the exact protection depends on the system's configuration.

My confidence in using the Linux command line is improving as I learn to execute commands and check their output. I am becoming more familiar with Docker commands such as `docker run`, `docker ps`, and `docker logs`. When errors occur, I need to read the messages carefully and troubleshoot instead of immediately giving up. Overall, this activity helped me connect containerization with cloud storage and gave me more practice in documenting technical work.

## Personal Experience
[Add a few sentences describing what actually happened during your deployment, any error you encountered, and how you resolved it.]
