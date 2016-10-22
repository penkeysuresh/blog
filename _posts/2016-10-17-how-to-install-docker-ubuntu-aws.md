---
layout: post
title:  "But it works fine on my local..."
date:   2016-10-17 17:04:38 +0530
categories: docker, all
tags: docker
---

In recent times, there is a lot of buzz going on about the containers. Whether it be [Docker](https://www.docker.com/) or [Kubernetes](http://kubernetes.io/) or [OpenVZ](https://openvz.org/Main_Page) or other bunch of upcoming containers, all these containers are working towards solving one of the most fundamental problem developers face in their daily life... not working on server... but works fine on my local...

### Need for Containers
Containers are a long overdue items that are much needed and deserved by developers and system administrators, unlike The Dark Knight. Containers provide a self-sufficient environment for a software program to run in terms of OS, runtime, code and file system. 

Since the software is inside this container and not directly on the server, the software becomes independent to the server environment providing a guarantee that the software will work on any other server environment. (A <b>similar</b> abstraction that comes to my mind is a Java program, where the actual compiled code runs on a <b>JVM</b> which needs to be installed on the server, making it compile once and run anywhere, as long as a JVM in installed on the devise). 

This solution will solve two important aspects in Software Development :
- **Consistency** - no more mystery of things not working on a different environment
- **Easy replication** - since things are consistent, it's easier to copy now

As you have guessed by now, a consistent and easily replicable solution will provide the most coveted property for the software **scale**

### What is Docker ?
Docker is one of those containers that is open source, easy to use, and one that is also [very hot](https://github.com/docker/docker/pulse) at the moment. Docker project started about 3 years ago, hit it's major release about year later. Although the technology is very new, it has a very active community and it's updated very frequently. I happened to use it for one of my clients and it did make my life very easy, especially when the entire app had to be shifted from one server to another one.

### How to install Docker ?

* #### On vanilla ubuntu instance 
There are many ways to install docker on your linux machine. Easiest way probably is to run this command on your terminal

                    curl -sSL https://get.docker.com/ | sh

This will download and run the script present on [get.docker.com](https://get.docker.com/) which will install docker on your machine.

* #### Installing manually on ubuntu
If you are cautious about third party scripts, you can install docker manually on your ubuntu instance by following the this process that is outlined [in docker documentation](https://docs.docker.com/engine/installation/linux/ubuntulinux/). Below is a handy script that does exactly the same that is outlined on that page.
            <script src="https://gist.github.com/penkeysuresh/f248ae77e26b6474de27f0a9c9093718.js"></script>

* #### On Amazon Linux AMI instance
Amazon has built in package manager ``yum`` which makes it easier to install docker on Amazon Linux AMI instance. Below is the simple command that's install docker 

                    sudo yum install -y docker

### Create a docker group

Docker always runs as root and can be accessed via sudo. For all the cases it is advised to create a group docker and add it to sudo and add your user to docker group instead of using sudo every time.

Create docker group using 

                    sudo groupadd docker

Add your user to docker group using 

                    sudo usermod -aG docker $(whoami)