
# Mesos Container Service Walkthrough

This walkthrough assumes you have deployed an ACS cluster with a Mesos orchestrator using the template from [101-acs-mesos](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-mesos). For more detailed 

Once your container service has been created you will have a resource group containing 3 parts:

1. a set of 1,3, or 5 masters in a master specific availability set.  Each master's SSH can be accessed via the public dns address at ports 2200..2204

2. a set of agents in an Virtual Machine Scale Set (VMSS).  The agent VMs can be accessed through a master.  See [agent forwarding](https://github.com/Azure/azure-quickstart-templates/blob/master/101-acs-mesos/docs/SSHKeyManagement.md#key-management-and-agent-forwarding-with-windows-pageant) for an example of how to do this.

![Image of Mesos container service on azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-acs-mesos/images/mesos.png)


1. **Admin Router on port 80** - The admin router enables you to access all mesos services.  For example, if you create an SSH tunnel to port 80 you can access the services on the following urls:
  1. **Mesos** - <http://localhost/mesos/>
  2. **Marathon** - <http://localhost/marathon/>
  3. **Chronos** - <http://localhost/chronos/>
2. **Mesos on port 5050** - Mesos is the distributed systems kernel that abstracts cpu, memory and other resources, and offers these to services named "frameworks" for scheduling of workloads.
3. **Marathon on port 8080** - Marathon is a scheduler for Mesos that is equivalent to init on a single linux machine: it schedules long running tasks for the whole cluster.
4. **Chronos on port 4400** - Chronos is a scheduler for Mesos that is equivalent to cron on a single linux machine: it schedules periodic tasks for the whole cluster.
5. **Docker on port 2375** - The Docker engine runs containerized workloads and each Agent runs the Docker engine.  Mesos runs Docker workloads, and examples on how to do this are provided in the Marathon and Chronos walkthrough sections of this readme.


All VMs are in the same VNET where the masters are on private subnet 172.16.0.0/24 and the agents are on the private subnet, 10.0.0.0/8, and fully accessible to each other.

## Template Parameters
When you deploy the template you will need to specify the following parameters:
* `dnsNamePrefix`
