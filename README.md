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

Now for formally defining what Docker is :
Docker is an open platform for developing, shipping, and running applications.

<h2>Docker: Develop once,Run anywhere.</h2>


![runshipanywhere](https://github.com/gvinothan/Docker/assets/43309736/6fb1badb-f056-4d26-baf7-08cfa9beb91e)

You can download and install Docker on multiple platforms.

<h3>It works on my computer!</h3>

Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. By taking advantage of its methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

Docker eliminates, “But it works on my computer!” nightmares during deployments, by exactly mirroring development and production environments.


![devops](https://github.com/gvinothan/Docker/assets/43309736/d39e8ba0-c00e-4e7a-a78f-ab14b839205c)


Source: Thanks google search engine, image owner and various article.
