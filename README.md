# docker

Docker Architecture and Components

1. Docker Daemon (`dockerd`):
- 𝗥𝗼𝗹𝗲: Manages Docker containers on a system.
- 𝗥𝗲𝘀𝗽𝗼𝗻𝘀𝗶𝗯𝗶𝗹𝗶𝘁𝗶𝗲𝘀: Building, running, and managing containers.
  
2. Docker Client (`docker`):
- 𝗥𝗼𝗹𝗲: Interface through which users interact with Docker.
- 𝗖𝗼𝗺𝗺𝗮𝗻𝗱𝘀: build, pull, run, etc.
  
3. Docker Images:
- 𝗗𝗲𝗳𝗶𝗻𝗶𝘁𝗶𝗼𝗻: Read-only templates used to create containers.
- 𝗥𝗼𝗹𝗲: Serve as the basis for creating containers.
- 𝗥𝗲𝗴𝗶𝘀𝘁𝗿𝘆/𝗛𝘂𝗯: A storage and distribution system for Docker images.

4. Docker Containers:
- 𝗗𝗲𝗳𝗶𝗻𝗶𝘁𝗶𝗼𝗻: Runnable instances of Docker images.
- 𝗥𝗼𝗹𝗲: Encapsulate the application and its environment.

5. Docker Registry:
- 𝗥𝗼𝗹𝗲: Store Docker images.
- 𝗣𝘂𝗯𝗹𝗶𝗰 𝗥𝗲𝗴𝗶𝘀𝘁𝗿𝘆: Docker Hub.
- 𝗣𝗿𝗶𝘃𝗮𝘁𝗲 𝗥𝗲𝗴𝗶𝘀𝘁𝗿𝘆: Can be hosted by users.
 

Docker Workflow

A. Development Phase

1. 𝗪𝗿𝗶𝘁𝗲 𝗖𝗼𝗱𝗲:
   - Developers write code locally.
   
2. 𝗕𝘂𝗶𝗹𝗱 𝗗𝗼𝗰𝗸𝗲𝗿 𝗜𝗺𝗮𝗴𝗲:
   - 𝗗𝗼𝗰𝗸𝗲𝗿𝗳𝗶𝗹𝗲: A script with instructions to create a Docker image.
   - 𝗖𝗼𝗺𝗺𝗮𝗻𝗱: `docker build -t my-image .`
   
3. 𝗧𝗲𝘀𝘁 𝗟𝗼𝗰𝗮𝗹𝗹𝘆:
   - Run the application inside a Docker container locally.
   - 𝗖𝗼𝗺𝗺𝗮𝗻𝗱: `docker run my-image`
   
B. Share/Deploy Phase

4. 𝗣𝘂𝘀𝗵 𝗜𝗺𝗮𝗴𝗲 𝘁𝗼 𝗥𝗲𝗴𝗶𝘀𝘁𝗿𝘆:
   - Push the Docker image to a registry (Docker Hub, AWS ECR, etc.).
   - 𝗖𝗼𝗺𝗺𝗮𝗻𝗱: `docker push my-image`
   
5. 𝗗𝗲𝗽𝗹𝗼𝘆 𝗼𝗻 𝗮 𝗦𝗲𝗿𝘃𝗲𝗿/𝗖𝗹𝘂𝘀𝘁𝗲𝗿:
   - Pull the Docker image from the registry.
   - 𝗖𝗼𝗺𝗺𝗮𝗻𝗱: `docker pull my-image`
   - Run the container on a server or a cluster (like Kubernetes).
   - 𝗖𝗼𝗺𝗺𝗮𝗻𝗱: `docker run my-image`

C. CI/CD Integration

6. 𝗖𝗼𝗻𝘁𝗶𝗻𝘂𝗼𝘂𝘀 𝗜𝗻𝘁𝗲𝗴𝗿𝗮𝘁𝗶𝗼𝗻 (𝗖𝗜):
   - Integrate code changes and build the Docker image.
   - Push the built image to a registry.
   
7. 𝗖𝗼𝗻𝘁𝗶𝗻𝘂𝗼𝘂𝘀 𝗗𝗲𝗽𝗹𝗼𝘆𝗺𝗲𝗻𝘁 (𝗖𝗗):
   - Deploy the Docker image from the registry to production environments.
   
D. Scaling & Management

8. 𝗦𝗰𝗮𝗹𝗶𝗻𝗴:
   - Increase or decrease the number of running containers based on demand.
   
9. 𝗠𝗼𝗻𝗶𝘁𝗼𝗿𝗶𝗻𝗴 & 𝗟𝗼𝗴𝗴𝗶𝗻𝗴:
   - Track the performance and logs of running containers.

10. 𝗨𝗽𝗱𝗮𝘁𝗲 & 𝗥𝗼𝗹𝗹𝗯𝗮𝗰𝗸:
   - Deploy updates by pushing new Docker images to the registry and updating running containers.
   - Rollback to a previous version if needed by running containers from an older Docker image.

E. Networking & Storage

11. 𝗡𝗲𝘁𝘄𝗼𝗿𝗸𝗶𝗻𝗴:
   - Manage communication between containers and the outside world.

12. 𝗦𝘁𝗼𝗿𝗮𝗴𝗲:
   - Manage data and persist state using volumes.
