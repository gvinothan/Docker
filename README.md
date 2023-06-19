<h1>Containerization:</h1>
Containerization is operating system-level virtualization or application-level virtualization over multiple network resources so that software applications can run in isolated user spaces called containers in any cloud or non-cloud environment, regardless of type or vendor.

<h1>What is docker?</h1>

Let’s first understand what Cloud Computing is.

Cloud computing is the on-demand availability of computer system resources, especially data storage and computing power, without direct active management by the user. Large clouds often have functions distributed over multiple locations, each of which is a data center.

In simple terms, it refers to both the applications delivered as services over the Internet and the hardware and system software in the data centers that provide those services.

![CloudComputing](https://github.com/gvinothan/Docker/assets/43309736/0cf8cbd6-919b-42a2-a264-9dc549abef10)

Docker in cloud computing is a technology, which has undoubtedly taken an evolutionary step towards the management of deployment platforms.

![docker](https://github.com/gvinothan/Docker/assets/43309736/5a16bb90-5164-4fea-9675-44e23a740b83)

Let’s start by considering an example where you would want to run multiple applications on the same host, but you want to keep them isolated from each other, and hence you have two different virtual machines in the host. But VMs consume resources and lowers performance.

![vmdocker](https://github.com/gvinothan/Docker/assets/43309736/13a218bc-aa5c-4059-8b45-1f1716c0fc77)


Virtual machines have a full OS with its memory management installed with the associated overhead of virtual device drivers. It quickly adds up to a lot of RAM and CPU cycles. It is still economical than running separate actual computers but, for some applications it is still overhead.

Here the containers come into view. There are two known types of containers:

<h5>Linux Containers:</h5> The original container technology is Linux Containers, commonly known as LXC. LXC is a Linux operating system-level virtualization method for running multiple isolated Linux systems on a single host.
<h5>Docker:</h5> Docker also used LXC in its initial stages but later morphed into its own container runtime environment. Docker separated itself from the pack by offering an entire ecosystem for container management.

Containers are a better choice when your biggest priority is maximizing the number of applications running on a minimal number of servers.

Now for formally defining what Docker is
Docker is an open platform for developing, shipping, and running applications.

<h2>Docker: Develop once,Run anywhere.</h2>


![runshipanywhere](https://github.com/gvinothan/Docker/assets/43309736/6fb1badb-f056-4d26-baf7-08cfa9beb91e)

You can download and install Docker on multiple platforms.

<h3>It works on my computer!</h3>

Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. By taking advantage of its methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

Docker eliminates, “But it works on my computer!” nightmares during deployments, by exactly mirroring development and production environments.


![devops](https://github.com/gvinothan/Docker/assets/43309736/d39e8ba0-c00e-4e7a-a78f-ab14b839205c)

<h1>Understanding the Dockerfile</h1>

  1.  Docker builds images automatically by reading the instructions from a Dockerfile.
  2.  It is a text file without any .txt extensions that contains all commands in order, needed to build a given image.
  3.  It is always named Dockerfile.

Docker image consists of read-only layers each of which represents a Dockerfile instruction. The layers are stacked and each one is created by the change from the previous layer. For example, if I create a base layer of ubuntu and then in second instruction I install Python it will create a second layer. Likewise, if I do any changes by the instructions(RUN , COPY , ADD) it will create a new layer in that image.

Containers are read-write layers that are created by docker images.

In simple words, a Dockerfile is a set of instructions that creates a stacked-layer for each instruction that collectively makes an image(which is a prototype or template for containers)

![dockerlayer](https://github.com/gvinothan/Docker/assets/43309736/76812391-0d21-459a-82f4-297e54de5b4c)

<h3>Frequently used Dockerfile commands</h3>

FROM   Defines a base image, it can be pulled from docker hub (For example- if we want to create a javascript application with node as backend then we need to have node as a base image, so it can run node application.)

RUN Executes command in a new image layer (we can have multiple run commands)

CMD Command to be executed when running a container (It is asked to have one CMD command, if a Dockerfile has multiple CMDs, it only applies the instructions from the last one.

EXPOSE  Documents which ports are exposed (It is only used for documentation)

ENV Sets environment variables inside the image

COPY It is used to copy your local files/directories to Docker Container.

ADD  It is more feature-rich version of the COPY instruction. COPY is preferred over ADD. Major difference b/w ADD and COPY is that ADD allows you to copy from URL that is the source can be URL but in COPY it can only have local ones.

ENTRYPOINT  Define a container's executable (You cannot override and ENTRYPOINT when starting a container unless you add the --entrypoint flag.)

VOLUME  It defines which directory in an image should be treated as a volume. The volume will be given a random name which can be found using docker inspect command.

WORKDIR Defines the working directory for subsequent instructions in the Dockerfile(Important point to remember that it doesn't create a new intermediate layer in Image)

    
![dockerfile](https://github.com/gvinothan/Docker/assets/43309736/0991a86c-1411-483c-88c8-844d11c8ffa3)

<h3>This is a sample Dockerfile:</h3>

```

FROM ubuntu

RUN apt-get update

RUN apt-get install –y nginx

CMD [“echo”,”First Container Image created”].
```

<h3>Each instruction creates one layer</h3>

FROM creates a layer from the ubuntu:18.04 Docker image.

COPY adds files from your Docker client’s current directory.

RUN builds your application with make.

CMD specifies what command to run within the container.

Let's see this demo example of Docker layer architecture-


![imagelayer](https://github.com/gvinothan/Docker/assets/43309736/11337408-5589-4793-8993-cf7b7871424d)

<h3>Difference between RUN,CMD and ENTRYPOINT?</h3>

RUN - RUN instruction allows you to install your application and packages required for it. It executes any commands on top of the current image and creates a new layer by committing the results. Often you will find multiple RUN instructions in a Dockerfile.

```
RUN apt-get install python
```

CMD - CMD instruction allows you to set a default command, which will be executed only when you run container without specifying a command. If Docker container runs with a command, the default command will be ignored. If Dockerfile has more than one CMD instruction, all but last CMD instructions are ignored.

```
 CMD "echo" "Hello World!"
```

ENTRYPOINT ENTRYPOINT instruction allows you to configure a container that will run as an executable. It looks similar to CMD, because it also allows you to specify a command with parameters. The difference is ENTRYPOINT command and parameters are not ignored when Docker container runs with command line parameters.

Prefer ENTRYPOINT to CMD when building executable Docker image and you need a command always to be executed. Additionally use CMD if you need to provide extra default arguments that could be overwritten from command line when docker container runs.

Choose CMD if you need to provide a default command and/or arguments that can be overwritten from command line when docker container runs.

Source: Thanks google search engine, image owner and various article.
