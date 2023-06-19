<h1>What is docker?<h1?

Let’s first understand what Cloud Computing is.

So the formal definition provided by NIST is as follows:-
Cloud Computing is a model for enabling ubiquitous, convenient,on-demand network access to a shared pool of configurable computing resources that can be rapidly provisioned and released with minimal management effort or service provider interaction.

In simple terms, it refers to both the applications delivered as services over the Internet and the hardware and system software in the data centers that provide those services.

Docker in cloud computing is a technology, which has undoubtedly taken an evolutionary step towards the management of deployment platforms.

Let’s start by considering an example where you would want to run multiple applications on the same host, but you want to keep them isolated from each other, and hence you have two different virtual machines in the host.
But VMs consume resources and lowers performance.

Virtual machines have a full OS with its memory management installed with the associated overhead of virtual device drivers. It quickly adds up to a lot of RAM and CPU cycles. It is still economical than running separate actual computers but, for some applications it is still overhead.

Here the containers come into view. There are two known types of containers:

    Linux Containers:-The original container technology is Linux Containers, commonly known as LXC. LXC is a Linux operating system-level virtualization method for running multiple isolated Linux systems on a single host.
    Docker:- Docker also used LXC in its initial stages but later morphed into its own container runtime environment. Docker separated itself from the pack by offering an entire ecosystem for container management.

Containers are a better choice when your biggest priority is maximizing the number of applications running on a minimal number of servers.

Now for formally defining what Docker is :
Docker is an open platform for developing, shipping, and running applications.

Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. By taking advantage of its methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

Docker eliminates, “But it works on my computer!” nightmares during deployments, by exactly mirroring development and production environments.
Docker: Develop once,Run anywhere.

You can download and install Docker on multiple platforms.

Let us clarify some of the concepts of Docker:-

    Docker Image:- A Docker image is an immutable file that contains the source code, libraries, dependencies, tools, and other files needed for an application to run. It is a read-only template with instructions for creating a Docker container.Often a docker image is based on another docker image. For example, an image which is an Ubuntu image, but it also installs Apache Web Server and application as well as configuration details required to make your application run.
    Docker Container:- A container is a runnable instance of an image. You can create, start, stop, move, or delete a container using the Docker API or CLI. You can connect a container to one or more networks, attach storage to it, or even create a new image based on its current state. It runs as a discrete process on the host machine.
    Docker File:- Docker can build images automatically by reading the instructions from a Docker file. A Docker file is a text document that contains all the commands a user could call on the command line to assemble an image.

The underlying technology of Docker

Docker is written in the Go programming language and takes advantage of several features of the Linux kernel to deliver its functionality.

    Namespaces: Docker makes use of kernel namespaces to provide an isolated workspace(container). Docker Engine uses namespaces such as the following on Linux:

a. PID namespace for process isolation.

b. NET namespace for managing network interfaces.

c. IPC namespace for managing access to IPC resources.

d. MNT namespace for managing file system mount points.

e. UTS namespace for isolating kernel and version identifiers

2. Control groups: Docker also makes use of kernel control groups for resource allocation and isolation.A cgroup limits an application to a specific set of resources.It allows Docker engine to share available hardware resources with containers and optionally enforce limits and constraints.

3. Union file Systems: Union file systems, or UnionFS, are file systems that operate by creating layers, making them very lightweight and fast. Docker engine uses UnionFS to provide the building blocks for containers.It is used to avoid duplicating a complete set of files each time you run an image as a new container.
