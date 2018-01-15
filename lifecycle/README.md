# Lifecycle Model

A VNF/application typically has to support following standard lifecycle management procedures:

* **Onboarding**  
  Receive and validate a specific version of a VNF/application from a supplier and
  upload the corresponding artefacts to a repository
* **Deployment**  
  Initial installation of a specific version of a VNF/application into a cloud environment.
* **Scale-In**  
  Capacity extension of horizontally scalable component of a VNF/application.
* **Scale-Out**  
  Capacity decrease of horizontally scalable component of a VNF/application.
* **Healing**  
  Compensation of the loss a node of a component of a VNF/application.
* **Upgrade**  
  Rolling upgrade of the cluster of nodes of a component of a VNF/application.
* **Migration**  
  Shift of a node of a component of VNF/application to another host within a cloud environment.
* **Destroy**  
  Shutdown of a VNF/application and release of all related infrastructure resources.
* **Inventory**  
  Generate a report of all nodes/components of a VNF/application along with their runtime attributes (e.g. IP-addresses).
* **Status**  
  Status of a node/component of a VNF/application,
