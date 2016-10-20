---
layout: post
title:  "But it works fine on my local..."
date:   2016-10-17 17:04:38 +0530
categories: docker
---

In recent times, there is a lot of buzz going on about the containers. Whether it be [Docker](https://www.docker.com/) or [Kubernetes](http://kubernetes.io/) or [OpenVZ](https://openvz.org/Main_Page) or other bunch of upcoming containers, all these containers are working towards solving one of the most fundamental problem developers face in their daily life... not working on server... but works fine on my local...


### Need for Containers

Containers are a long overdue items that are much needed and deserved by developers and system administrators... unlike The Dark Knight. Containers provide a self-sufficient environment for a software to run (in terms of os, runtime, code and system tools). Since the software is inside this container (on a server) there is a gaurentee that this will work on any other server or environment (as long as the wrapping container is same). 

This solution will solve three important aspects in Software Development :

- **Consistency** - no more mystery of things not working on a diffrent environment
- **Easy replication** - since things are consistent, it's easier to copy now

As you have guessed by now, a consistent and easily replicable solution will provide the most coveted property for the software **scale**


### What is Docker
Docker is one of those containers that is open source, easy to use, and one that is also [hot](https://github.com/docker/docker/pulse) at the moment. I happened to use it for one of my clients and it did make my life very easy, especially when the entire app had to be shifted from one server to another one. Twice. In a month.


### On vanilla ubuntu instance
There are many ways to install docker on your linux mechine. Easiest way probably is to run this command on your terminal

                    curl -sSL https://get.docker.com/ | sh

This will download and run the script present on [get.docker.com](https://get.docker.com/) which will install docker on your mechine.

### On ubuntu using manual script
If you are cautious about third party scripts, you can use the below script to install docker on your ubuntu instance. This process is outlined [here](https://docs.docker.com/engine/installation/linux/ubuntulinux/) in docker documentation. Replace ``[****]`` in line 7 of the below script by "trusty" for 14.04, "xenial" for 16.04 based on your ubuntu version
<script src="https://gist.github.com/penkeysuresh/f248ae77e26b6474de27f0a9c9093718.js"></script>



### On amazon linux AMI instance
Amazon has built in package manager ``yum`` which makes it easier to intsall docker on Amazon Linux AMI instance. Below is the simple command that's install docker 

                    sudo yum install -y docker


For both the cases it is important to add your user to ``docker`` user group to make docker management easier. You can add your user to docker group using ``sudo usermod -aG docker $(whoami)``