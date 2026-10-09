# Mission Reflection

## 1. Docker Containers vs. Virtual Machines

I learned that Docker containers usually start much faster than virtual machines because they do not need to boot a separate guest operating system. A virtual machine requires its own operating system installation and configuration, while a container uses an image that packages the application and its dependencies. This makes containers convenient for deploying web applications quickly and consistently.

## 2. Importance of Port Mapping

Port mapping is necessary because applications running inside a container are accessed through network ports. The command `-p 8080:80` maps port 8080 on the host to port 80 inside the container. This allows a user to access the Nginx web server through `http://localhost:8080` when the environment supports local access. Without the appropriate port mapping, the service may not be reachable through that host port.

## 3. What Happens When a Container Is Removed?

The command `docker rm` removes a stopped container and its writable container layer. Data stored only in that layer may be lost when the container is removed. Data stored in persistent volumes or outside the container may remain available. This taught me why persistent storage should be planned carefully when deploying applications that need to retain important information.

## 4. Containerization and DevOps

Containerization helps developers and IT operations teams work together by packaging applications and their dependencies into consistent images. Developers can build and test the same image that operations teams deploy, reducing differences between development and production environments. Containers also support automated deployment processes and can be integrated into continuous integration and continuous delivery pipelines.

## 5. Improvement of My GitHub Portfolio

My GitHub Cloud Computing Portfolio continues to improve as I add organized folders, Markdown documentation, screenshots, and technical demonstrations. Laboratory Activity 4 adds practical evidence of my Docker skills, including image downloading, container deployment, port mapping, and lifecycle management. I am also learning the importance of meaningful commits and clear technical explanations.

## Conclusion

This mission helped me understand why containerization is important in modern cloud computing. I gained knowledge of Docker commands and learned how to deploy and manage an Nginx container. I will continue practicing these skills to improve my understanding of cloud-native applications and DevOps workflows.
