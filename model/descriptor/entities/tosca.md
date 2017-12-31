TOSCA Simple Profile Version 1.0
=================================

TOSCA is used to capture the entities of the VNF model.   

These entities are basically described in yaml as a list of TOSCA nodes of a specific type.

This information suffices to derive all related entities such as security rules etc.

Structure
-----------------

<pre>
tosca_definitions_version: [TOSCA_dtag_profile_for_nfv_0_0_6]

description: [Description for this document]

metadata:
	template_name: [Name of the descriptor]
    ... additional metadata ...

topology_template:

	node_templates:

    [name of VNF]:
      type: tosca.dtag.nodes.VNF
      properties:
        ... list of properties ...

    [name of tenant]:
      type: tosca.dtag.nodes.Tenant
      properties:
        ... list of properties ...

    [name of network]:
      type: tosca.dtag.nodes.Network
      properties:
        ... list of properties ...

    [name of external component]:
      type: tosca.dtag.nodes.ExternalComponent
      properties:
        ... list of properties ...
      capabilities:
        ... list of capabilities ...
      requirements:
        ... list of requirements ...

    [name of internal component]:
      type: tosca.dtag.nodes.InternalComponent
      properties:
        ... list of properties ...
      capabilities:
        ... list of capabilities ...
      requirements:
        ... list of capabilities ...
</pre>


Entities:
---------

The TOSCA based VNF descriptor makes use of following entities

- **VNF**: a virtual network function   
	type: tosca.dtag.nodes.VNF   
  [Specification ...](vnf.md)  
- **Tenant**:  a virtual datacenter    
	tosca.dtag.nodes.Tenant    
  [Specification ...](tenant.md)  
- **Network**:  a virtual L2/L3 overlay network    
	tosca.dtag.nodes.Network    
  [Specification ...](network.md)  
- **External Component**: an external communication partners    
	tosca.dtag.nodes.ExternalComponent   
  [Specification ...](externalcomponent.md)  
- **Internal Component**: a cluster of virtual servers    
	tosca.dtag.nodes.InternalComponent    
  [Specification ...](internalcomponent.md)  


**Links**:   
[Reference: YAML](http://yaml.org/spec/1.2/spec.html)    
[Reference: TOSCA Specification](http://docs.oasis-open.org/tosca/TOSCA-Simple-Profile-YAML/v1.0/TOSCA-Simple-Profile-YAML-v1.0.html)
