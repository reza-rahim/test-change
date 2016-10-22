# Microservice Framework - Mesos/Marathon, Docker, Weave and Flocker

1. **Docker:** Docker is a tool that allows developers, sys-admins etc. to easily deploy their applications in a sandbox (called containers) to run on the host operating system i.e. Linux.
2. **Mesos:** Apache Mesos is a centralised fault-tolerant cluster manager. It’s designed for distributed computing environments to provide resource isolation and management across a cluster of slave nodes.
  
  A Mesos cluster is made up of four major components:
  1. **ZooKeepers**
  2. **Mesos masters**
  3. **Mesos slaves**
  4. **Frameworks**

3. **Marathon:**  Mesos only provides the basic “kernel” layer of your cluster. Marathon framework is the equivalent of the Linux upstart or init daemons, designed for long-running applications.
