# VNF Lifecycle

The orchestrator will need to implement following use cases which are essential for the management of the lifecycle of VNFs/applications:

**Orchestration Use-Cases:**

**Onboarding**: handover of a new version of a VNF/application or one of its components,
**Deployment**: installation of a specific version of a VNF/application or one of its components within a tenant,
**Scale-In**: decreasing the capacity of a VNF/application by removing nodes of a component within a tenant,
**Scale-Out**: increasing the capacity of a VNF/application by adding nodes to a component within a tenant,

**Inventory**: derive the current status of a VNF/application within a tenant,
**Clean-Up**: completely remove all virtual resources of a tenant,

**Administration Use-Cases**:

**Administration**: creation of accounts and configuration of access rights,
Deploy: automatically deployment of the orchestrator tool suite into a cloud environment,
Backup: regularly saving the information which is held in the repositories of the orchestrator to an external data store, Recover: provide a mechanism for the orchestrator tool suite which allows to perform disaster recovery,
Migrate: shift the orchestrator to another runtime environment while maintaining it's service availability and
Upgrade: upgrade the orchestrator to a new version while maintaining it's service availability.
Each of these use cases is described in more detail in the following sections:
