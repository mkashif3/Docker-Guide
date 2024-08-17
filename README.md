# Docker-Guide
This is a quick guide for someone looking to start the journey in Containerisation! welcome!

## ** Docker overview **
Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker's methodologies for shipping, testing, and deploying code, you can significantly reduce the delay between writing code and running it in production.

# The Docker platform
Docker provides the ability to package and run an application in a loosely isolated environment called a container. The isolation and security lets you run many containers simultaneously on a given host. Containers are lightweight and contain everything needed to run the application, so you don't need to rely on what's installed on the host. You can share containers while you work, and be sure that everyone you share with gets the same container that works in the same way.

# What can I use Docker for?
Fast, consistent delivery of your applications
Docker streamlines the development lifecycle by allowing developers to work in standardized environments using local containers which provide your applications and services. Containers are great for continuous integration and continuous delivery (CI/CD) workflows.

# Responsive deployment and scaling
Docker's container-based platform allows for highly portable workloads. Docker containers can run on a developer's local laptop, on physical or virtual machines in a data center, on cloud providers, or in a mixture of environments.
Docker's portability and lightweight nature also make it easy to dynamically manage workloads, scaling up or tearing down applications and services as business needs dictate, in near real time.

# **Docker architecture**
Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface. Another Docker client is Docker Compose, that lets you work with applications consisting of a set of containers.

![image](https://github.com/user-attachments/assets/8c8c62c3-a66b-4dd1-91dc-4048057042be)

## The Docker daemon
The Docker daemon (dockerd) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services.

## The Docker client
The Docker client (docker) is the primary way that many Docker users interact with Docker. When you use commands such as docker run, the client sends these commands to dockerd, which carries them out. The docker command uses the Docker API. The Docker client can communicate with more than one daemon.

## Docker Desktop
Docker Desktop is an easy-to-install application for your Mac, Windows or Linux environment that enables you to build and share containerized applications and microservices. Docker Desktop includes the Docker daemon (dockerd), the Docker client (docker), Docker Compose, Docker Content Trust, Kubernetes, and Credential Helper. For more information, see Docker Desktop.

## Docker registries
A Docker registry stores Docker images. Docker Hub is a public registry that anyone can use, and Docker looks for images on Docker Hub by default. You can even run your own private registry.

When you use the docker pull or docker run commands, Docker pulls the required images from your configured registry. When you use the docker push command, Docker pushes your image to your configured registry.

## Docker objects
When you use Docker, you are creating and using images, containers, networks, volumes, plugins, and other objects. This section is a brief overview of some of those objects.

## Images
An image is a read-only template with instructions for creating a Docker container. Often, an image is based on another image, with some additional customization. For example, you may build an image which is based on the ubuntu image, but installs the Apache web server and your application, as well as the configuration details needed to make your application run.

You might create your own images or you might only use those created by others and published in a registry. To build your own image, you create a Dockerfile with a simple syntax for defining the steps needed to create the image and run it. Each instruction in a Dockerfile creates a layer in the image. When you change the Dockerfile and rebuild the image, only those layers which have changed are rebuilt. This is part of what makes images so lightweight, small, and fast, when compared to other virtualization technologies.

## Containers
A container is a runnable instance of an image. You can create, start, stop, move, or delete a container using the Docker API or CLI. You can connect a container to one or more networks, attach storage to it, or even create a new image based on its current state.

By default, a container is relatively well isolated from other containers and its host machine. You can control how isolated a container's network, storage, or other underlying subsystems are from other containers or from the host machine.

## Container images
If you’re new to container images, think of them as a standardized package that contains everything needed to run an application, including its files, configuration, and dependencies. These packages can then be distributed and shared with others.

## Docker Hub
To share your Docker images, you need a place to store them. This is where registries come in. While there are many registries, Docker Hub is the default and go-to registry for images. Docker Hub provides both a place for you to store your own images and to find images from others to either run or use as the bases for your own images.

### Docker Commands
Now let's start with some commands used in Docker. Each command has an example below:

## 1- Docker Build : Build an image from a Dockerfile.
This command constructs a new Docker image based on instructions provided in a Dockerfile. It may involve installing dependencies, configuring the environment, and copying application code.

![Screenshot 2024-08-17 at 23 16 37](https://github.com/user-attachments/assets/f7b9d57c-7d9e-4fa6-a1d9-d081614f2a6d)

## 2- Docker images
This command displays a collection of Docker images stored locally. It showcases information like image ID, repository, and tag.

![Screenshot 2024-08-17 at 23 18 42](https://github.com/user-attachments/assets/f1d50df4-c593-48bf-bca9-22bfe8502344)

## 3- Docker pull
This command retrieves a Docker image from a registry to the local system. This enables obtaining a remotely stored image for running containers on the local machine.

![Screenshot 2024-08-17 at 23 19 57](https://github.com/user-attachments/assets/a2384219-77f9-43a5-8c3a-b58f63797471)

## 4- Docker rm
This command deletes one or more stopped containers from the system. It aids in removing unnecessary containers and performing clean-up tasks.

![Screenshot 2024-08-17 at 23 21 34](https://github.com/user-attachments/assets/3cf481f0-d6cf-498f-aec0-325897f5ec1c)

or

![Screenshot 2024-08-17 at 23 21 58](https://github.com/user-attachments/assets/0d5a3e64-7720-4ff1-9ef2-73b8a0e8d73a)

## 5- Tag an Image

![Screenshot 2024-08-17 at 23 23 19](https://github.com/user-attachments/assets/e70be73d-491b-4c3c-943b-644b28d8a422)

## 6- Docker push
This command uploads a Docker image to a registry, like Docker Hub or a private registry. This facilitates sharing the image with others or deploying it in different environments

![Screenshot 2024-08-17 at 23 25 18](https://github.com/user-attachments/assets/e861f305-dc5a-48ba-a3a8-4d5206928890)

## 7- Docker inspect
This command provides detailed information about Docker objects, including containers, images, networks, and volumes. It offers an extensive view of configuration, network settings, and other objectspecific details.

![Screenshot 2024-08-17 at 23 26 10](https://github.com/user-attachments/assets/03c6532b-ecf2-42f6-9db8-30d0c5ff79ed)

## 8- Docker run
This command initiates creating and activating a fresh container using a Docker image. It provides options to configure aspects like port mappings, environment variables, and volume mounts.
For instance, the Docker run -d option is used to run a container in detached mode. When the Docker -d command is selected, the container operates in the background, enabling you to keep using the command prompt or the terminal without being connected to the container’s console.

![Screenshot 2024-08-17 at 23 27 29](https://github.com/user-attachments/assets/cd70d1e4-618b-4c0c-a8b8-4ec9eb8f6344)

## 9- Run a named container from image

![Screenshot 2024-08-17 at 23 28 25](https://github.com/user-attachments/assets/d76544e9-54a6-4bbd-b72b-81567ddcd939)

## 10- Docker ps
The “docker ps” command is used to present data regarding the active containers on a Docker host. It offers insights such as container ID, utilised image, container status, port mapping, and resource usage. This command aids in monitoring running containers and acquiring vital information for Docker environment management.

![Screenshot 2024-08-17 at 23 29 07](https://github.com/user-attachments/assets/d353fe58-14a3-4e51-bdb3-3f88734ac84d)

To list all containers including ones thch are stopped.

![Screenshot 2024-08-17 at 23 29 54](https://github.com/user-attachments/assets/cb20c664-6d1a-4e80-b1eb-4354178ac99a)

## 11- Docker stop all containers
This command is employed to halt all active containers simultaneously. By combining commands, it retrieves the IDs of running containers and then passes them to the “docker stop” command. Consequently, all currently running containers on the Docker host are stopped, offering a convenient means to halt multiple containers simultaneously.

![Screenshot 2024-08-17 at 23 31 53](https://github.com/user-attachments/assets/993dbdab-2bed-4c13-84d9-aebbbb82ad47)

replace stop with start to restart a stopped container.

![Screenshot 2024-08-17 at 23 31 26](https://github.com/user-attachments/assets/f461f13e-2948-4f06-9d37-6dea17f1fa0a)

## 12- Run a container in interactive mode

![Screenshot 2024-08-17 at 23 33 45](https://github.com/user-attachments/assets/5a0c8a5b-393c-4110-8f54-c60578099c3f)

## 13- Docker rm
This command deletes one or more stopped containers from the system. It aids in removing unnecessary containers and performing clean-up tasks.

![Screenshot 2024-08-17 at 23 34 27](https://github.com/user-attachments/assets/39f9b9d3-e027-4992-8943-953e0ecf3a62)

To remove forcefully!

![Screenshot 2024-08-17 at 23 35 07](https://github.com/user-attachments/assets/ebcd3e40-c277-4270-b1ae-1d05986380ff)

## 14- Docker inspect
This command provides detailed information about Docker objects, including containers, images, networks, and volumes. It offers an extensive view of configuration, network settings, and other objectspecific details.

![Screenshot 2024-08-17 at 23 36 02](https://github.com/user-attachments/assets/fa4fcb71-d1a6-4839-9f65-ad14e2e168f0)

## 15- Docker logs
This command retrieves container-generated logs, displaying output and error messages. This aids in troubleshooting and debugging by providing insights into a running container’s activities.

![Screenshot 2024-08-17 at 23 36 42](https://github.com/user-attachments/assets/a7a3024c-422c-42e1-a24f-3e5807f891f5)

## 16- Docker stats 
This command provides real-time statistics of your running Docker containers. It displays various metrics, such as CPU usage, memory usage, network I/O, and block I/O for each container, allowing you to monitor the performance of your containers.

## 17- Create a named Volume
![Screenshot 2024-08-17 at 23 40 42](https://github.com/user-attachments/assets/dc7961d5-033f-4ff6-8f8f-d6df5b4da1f9)

## 18- List all volumes

![Screenshot 2024-08-17 at 23 42 20](https://github.com/user-attachments/assets/ebf127de-3c79-45e4-91be-23b4e642c54f)

## 19- Run a container with Volume

![Screenshot 2024-08-17 at 23 43 07](https://github.com/user-attachments/assets/400c53e4-a6af-46e9-bc4f-831531e4e206)

## 20- Copy files between container and volume

![Screenshot 2024-08-17 at 23 43 50](https://github.com/user-attachments/assets/a2786f5e-6820-4fa5-8828-ef5bf16533ca)

## 21- Run a container with port mapping

![Screenshot 2024-08-17 at 23 45 52](https://github.com/user-attachments/assets/f440d77e-d4de-4def-8bbd-f678c2d362ea)

## 22- List all networks

![Screenshot 2024-08-17 at 23 46 30](https://github.com/user-attachments/assets/fd9f6d93-823c-4edc-8e91-2e95514326f3)


# Dockerfile
A Dockerfile is a script-like text file that contains a set of instructions to build a Docker image. Docker images are the basis for running Docker containers, which are lightweight, portable, and self-sufficient environments that include everything needed to run a piece of software. 

## Key Components of a Dockerfile:

## 1- Base Image (FROM):
Every Dockerfile starts with a FROM instruction that specifies the base image for the new image. The base image can be any official image like ubuntu, node, python, etc., or a custom one.
Example:

FROM ubuntu:20.04

## 2- Maintainer (LABEL):
Optionally, you can add a LABEL to include metadata like the maintainer's name.
Example:

LABEL maintainer="yourname@example.com"

## 3- Working Directory (WORKDIR):
This sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions that follow it.
Example:

WORKDIR /app

## 4- Copying Files (COPY and ADD):
COPY copies files or directories from your local filesystem into the container.
ADD is similar but also allows you to extract tar files and download files from URLs.
Example:

COPY . /app

## 5- Running Commands (RUN):
RUN is used to execute commands during the image build process, like installing software.
Example:

RUN apt-get update && apt-get install -y python3

## 6- Environment Variables (ENV):
ENV is used to set environment variables within the container.
Example:

ENV NODE_ENV=production

## 7- Exposing Ports (EXPOSE):
EXPOSE informs Docker that the container will listen on the specified network ports at runtime.
Example:

EXPOSE 8080

## 8- Executing the Application (CMD and ENTRYPOINT):
CMD specifies the command to run when a container is started.
ENTRYPOINT is similar but sets the command that cannot be overridden by command-line arguments.
Example:

CMD ["python3", "app.py"]

## 9- Volume (VOLUME):
VOLUME is used to mount directories from the host filesystem into the container.
Example:

VOLUME ["/data"]

## Example of a Simple Dockerfile
Let’s say you have a simple Node.js application. Here’s what the Dockerfile might look like:

### #Use an official Node.js runtime as a parent image
FROM node:14

### #Set the working directory in the container
WORKDIR /usr/src/app

#### #Copy the local application files to the container’s working directory
COPY package*.json ./

### #Install dependencies
RUN npm install

### #Bundle app source code inside the container
COPY . .

### #The app binds to port 8080, so expose it
EXPOSE 8080

### #Define the command to run the application
CMD ["node", "app.js"]



# Summary:
**Dockerfile:** A set of instructions to build a Docker image.

**Image:** The blueprint of a container, created from a Dockerfile.

**Container:** A runtime instance of an image that runs the application or service.

**Commands:** FROM, COPY, RUN, CMD, etc., define how to build and run the application inside the container.

Using Dockerfiles, you can automate the process of packaging your applications with their dependencies, ensuring consistency across development, testing, and production environments.

