VNF Descriptor
==============

The TOSCA Simple Profile V1.0 standard has been selected as the reference language for VNF descriptors. DTAG is introducing certain constraints to this specification which streamline the description to what is actually needed for managing the lifecycle of VNFs in DTAGs infrastructure cloud (this is due to the circumstance that the TOSCA standard is very flexible regarding what can be expressed).

This document will detail the basic concepts of how DTAG describe the architecture of VNFs and how these concepts are captured in TOSCA.

An example VNF descriptor supplements the document to help depict the concepts and serve as a template from which own models can be derived.

Resources
---------

A VNF is distributed over several tenants which comprise networks and clusters of nodes.

These nodes represent virtual machines which make use of a specific server setup (flavor), require an operating system (image), utilize block storage (volumes) and communicate via a set of ports (interfaces) which are attached to communication domains (networks).

Finally the actual software applications are deployed into these virtual machines. In case of appliances these applications will be merged into the images.

Therefore following types of resources need to be supported:
- **VNF**: virtualized network function
- **Network**: global, datacenter and tenant networks
- **Tenant**: virtualized datacenter
- **Cluster**: cluster of virtual machines/containers/…
- **Node**: virtualized machine/container/…
- **Volume**: storage block device
- **Interface**: network interface
- **Application**: processes running in the node
- **Security Group**: security group securing the interfaces
