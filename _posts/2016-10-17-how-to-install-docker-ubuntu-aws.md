---
layout: post
title:  "How to install Docker"
date:   2016-10-17 17:04:38 +0530
categories: docker
---
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