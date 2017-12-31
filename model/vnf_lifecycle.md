# VNF Lifecycle

The orchestrator will need to implement following use cases which are essential for the management of the lifecycle of VNFs/applications:
Orchestration Use-Cases:
Upload: uploading of a new version of the VNF/application or one of its components,
Install: installing a specific version of a VNF/application or one of its components,
Configure: configuring an installed VNF/application or one of its components,
Start: starting a configured and installed VNF/application or one of its components,
Stop: stopping an active VNF/application or one of its components,
Reconfigure: reconfiguring an installed VNF/application or one of its components,
Update: updating an active VNF/application or one of its components,
Uninstall: uninstalling a VNF/application or one of its components,
Clean-Up: removing a VNF/application or one if its components if they have run into the failed state and
Monitor: constantly monitoring the status of a VNF/application and its components and notifying in the case of critical events.
Administration Use-Cases:
Administration: creation of accounts and configuration of

access rights,
Deploy: automatically deployment of the orchestrator tool suite into a cloud environment,
Backup: regularly saving the information which is held in the repositories of the orchestrator to an external data store, Recover: provide a mechanism for the orchestrator tool suite which allows to perform disaster recovery,
Migrate: shift the orchestrator to another runtime environment while maintaining it's service availability and
Upgrade: upgrade the orchestrator to a new version while maintaining it's service availability.
Each of these use cases is described in more detail in the following sections:
