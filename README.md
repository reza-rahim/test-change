
# Mesos Container Service Walkthrough

This walkthrough assumes you have deployed an ACS cluster with a Mesos orchestrator using the template from [101-acs-mesos](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-mesos). For more detailed 

Once your container service has been created you will have a resource group containing 3 parts:

1. a set of 1,3, or 5 masters in a master specific availability set.  Each master's SSH can be accessed via the public dns address at ports 2200..2204

2. a set of agents in an Virtual Machine Scale Set (VMSS).  The agent VMs can be accessed through a master.  See [agent forwarding](https://github.com/Azure/azure-quickstart-templates/blob/master/101-acs-mesos/docs/SSHKeyManagement.md#key-management-and-agent-forwarding-with-windows-pageant) for an example of how to do this.
