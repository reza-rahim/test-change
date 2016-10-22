# Microservice Framework - Mesos/Marathon, Docker, Weave and Flocker

1. **Docker:** (https://www.docker.com/) Docker is a tool that allows developers, sys-admins etc. to easily deploy their applications in a sandbox (called containers) to run on the host operating system i.e. Linux.
2. **Mesos:** (http://mesos.apache.org/) Apache Mesos is a centralised fault-tolerant cluster manager. It’s designed for distributed computing environments to provide resource isolation and management across a cluster of slave nodes.
  
  A Mesos cluster is made up of four major components:
  1. **ZooKeepers**
  2. **Mesos masters**
  3. **Mesos slaves**
  4. **Frameworks** (such as Marathon )
  

3. **Marathon:** (https://mesosphere.github.io/marathon/) Mesos only provides the basic “kernel” layer of your cluster. Marathon framework is the equivalent of the Linux upstart or init daemons, designed for long-running applications. 

4. **Weave:** (https://www.weave.works/) Waeve is Software Defined Network (SDN) that provides a unique IP address to each Docker Container over multiple host machines by creating virtual network. As a result, Docker container can directly talk to other Docker Containers from different hosts. Besides that, Weave also provides a DNS like functionality, where Docker Containers can be discovered with DNS like name resolution. 

5. **Flocker:** (https://clusterhq.com/) Flocker is an open-source container data volume manager for Dockerized applications. It helps to move the external persistence volume with the container. For example, if a Docker Container moves from one host another host, Flocker would re-mount the existing volume to the container. So the statefull containers --like database -- can be moved with ease. 

## Overview of the Framework
![Image of System Architecture](https://github.com/reza-rahim/microservice/blob/master/picture/SystemArchitecture.png)
