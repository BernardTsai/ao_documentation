# Application Model

In order to better understand the role of the VNF/application Orchestrator it is important to first distinguish between the various elements which are required to create a customer service.

Very many different types of components need to work consistently together in order to provide such a service to the customers.
To reduce the complexity of this setup the solution architecture can be divided into
loosely coupled layers of components as depicted in the following diagram:

![VNF Architecture](../images/vnf_architecture.png)

The red line between the virtual layers and physical infrastructure layer highlights the necessity to decouple the slow lifecycle management processes of the physical infrastructure from the lifecycle management of the virtual components which need to react in an agile manner to customer demand, e.g. when additional capacities are required or new services and features are to be introduced.

Physical Infrastructure
-----------------------

The actual solution which provides the customer service  is based on a physical infrastructure consisting of network and data center equipment. Typically the lifecycle management processes for the physical infrastructure layer are slow, e.g. the provisioning of long-distance network links may require several months.
This layer needs to be setup in a standardised way so that it can serve as the foundation for all the virtual components which can now be dynamically provisioned and managed on top of it

Virtual Infrastructure
----------------------

The first virtualised layer above the physical infrastructure layer will provide virtualised infrastructure resources based on a cloud technology e.g. OpenStack in administration realms which may be regarded as virtualised data centers. Each of these virtual data centers may host their own overlay networks in which virtual servers together with their storage pools can be embedded.

VNFs/Applications
-----------------

In this architecture the VNFs/applications are simply software solutions which will be deployed in the aforementioned virtual data center structures.
These solutions will be provided by many different internal as well as external solution providers and need to be managed in uniform way by the operator. As such they each resemble a service platform which provide a specific set of services to the end-users.

Services
---------

The service layer finally represents all the services which are directly related to and consumed by an end-user.

Application Model
-----------------

VNF/application orchestration focuses on the lifecycle management of the resources of the VNF/application layer.

A comprehensive management of the runtime lifecycle of applications requires:

1. a detailed understanding of the structure of the application and its components,
2. a description of the relevant components,
3. a way of distinguishing these elements in an unambiguous way and
4. a model describing in which states the applications and its components may be
   and what kind of transitions between these states are allowed.

The standards described in the following sections structure the way applications
are handled by the orchestrator. VNFs which follow these standards will be much
easier to integrate into the general cloud automation framework.
