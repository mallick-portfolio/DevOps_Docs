# Docker 

### Topics that i will try to cover in this documentation


- [Section 1: Getting Started ](#section-1-getting-started)
- [Section 2: Docker Images and Containers ](#section-2-docker-images-and-containers)
- [Section 3: Managing Data and Working with Volums ](#section-1-docker-volume)
- [Section 4: Docker Networking ](#section-1-docker-networking)
- [Section 5: Work with multi container application ](#section-1-multi-layer)


## Section 1: Getting started

### What is Docker?
[Docker](https://docs.docker.com/) is a platform designed to help developers build, share, and run container applications.
In simple word Docker is a container technology or A tool for creating and managing containers

<p align="center">
  <img src="../../images/what_is_docker.png" alt="What is docker">
</p>

### Why Dockers?
Imagine you're developing a Node.js application using version 20.02. On your local machine, everything works perfectly because all the dependencies are compatible with this version of Node.js.

Now, you want to share your project with a friend who also wants to run it on their computer. However, your friend is using Node.js version 18.04. When they try to install the project's dependencies, they encounter errors because some of the dependencies are not compatible with Node.js 18.04. You suggest that they upgrade to Node.js version 20.02, but this introduces the hassle of setting up the right environment just to get the project running.

This is where Docker comes in. With Docker, you can package your application, along with all its dependencies, libraries, and the specific version of Node.js you’re using, into a container. You can then share this container with anyone, and they will be able to run your project without having to manually set up the same environment on their machine. Docker ensures that your software runs the same, regardless of where it's deployed.

### What is a Virtual Machine (VM)?

A Virtual Machine (VM) is a software-based emulation of a physical computer that runs its own operating system and applications. It behaves like a separate computer, even though it runs on top of an existing host system.

### Docker vs Virtual Machines (VMs) – Brief Summary

| Feature           | Docker                             | Virtual Machines (VMs)                  |
|-------------------|------------------------------------|-----------------------------------------|
| **Architecture**   | Containers share the host OS and are lightweight | Each VM runs a full guest OS, making them heavier |
| **Resource Usage** | Uses fewer resources (CPU, memory, storage) | Requires more resources due to full OS overhead |
| **Performance**    | Faster startup with minimal overhead | Slower startup and higher overhead |
| **Portability**    | Highly portable across Docker environments | Portable but more cumbersome with full OS |
| **Isolation**      | Provides process-level isolation | Stronger isolation by running separate OSes |
| **Use Cases**      | Best for scalable, cloud-native apps and microservices | Ideal for running multiple OSes or legacy apps |

For more understand
<p align="center">
  <img src="../../images/docker_vs_vm.png" alt="Docker vs VMs">
</p>


### Docker Engine Local Setup

To set up Docker Engine on your local PC, please follow the official Docker installation instructions for your operating system:

- **Ubuntu / Debian / Linux**: [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
- **Windows**: [Install Docker Desktop on Windows](https://docs.docker.com/desktop/install/windows-install/)
- **macOS**: [Install Docker Desktop on macOS](https://docs.docker.com/desktop/install/mac-install/)

<p align="center">
  <img src="../../images/docker_setup.png" alt="Docker setup">
</p>



## Section 2: Docker Images and Containers

### Docker Image: 
A Docker image is like a blueprint or a template that contains everything your application needs to run, including the application code, libraries, and dependencies. Think of it as a package that has all the necessary components to run your application.

### Docker Container: 
A Docker container is an instance of a Docker image. When you run a Docker container, you're essentially creating a copy of the Docker image. This copy is a self-contained environment where your application runs. Containers are like virtual machines, but much lighter and more efficient.

See the bellow image for more understanding. As well as you will understand more when you start working with Docker.

<p align="center">
  <img src="../../images/docker_images_containers.png" alt="Docker images and containers">
</p>

If you already install docker  on your local machine, you can start working with Docker. If not, you can install it.Install guidline (https://docs.docker.com/)

First we start from already created  Docker image. We can use the official Docker images or create our own. For official  Docker images, you can check the Docker Hub (https://hub.docker.com/)
<p align="center">
  <img src="../../images/docker_hub.png" alt="Docker hub">
</p>


Search for the image you want to use, and then you can pull it to your local machine. For example, if you want to use the official Python/Node image, you can pull it with the following command. I am  using Node as an example.

### Command to Pull a Docker Image

To pull the official Node.js Docker image to your local machine, use the following command:

```bash
docker pull node:latest
```
This command will download the latest version of the Node.js Docker image to your local machine. It will take few  moment to download the image depending  on your internet speed.
You will see  the following output:

<p align="center">
  <img src="../../images/docker/docker_official_image.png" alt="Docker official image pull">
</p>


You don't need to worry about anything what happening here. I will explain everything one by one. 

