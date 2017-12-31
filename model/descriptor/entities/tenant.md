Tenant
======

A tenant represents a virtualized datacenter which is used to
host virtual resources of a virtualized network function.
The node template is structured in the following manner:

<pre>
...
topology_template:
	node_templates:

    ...

		[name of tenant]:
			type: tosca.dtag.nodes.Tenant
			properties:
				name:	[name of tenant]
				version: [version of tenant]
				description: [description of tenant]
				vnf:	[name of VNF]   
        datacenter: [name of datacenter]
        keys: |
          [yaml list of lines with SSH public keys]
    ...
</pre>


Properties
----------

This entity has following properties:

**name**: the name of the virtual network function   

This property needs to fulfill following constraints:
- is a string
- needs to match the id of the node
- should be a unique name within the TOSCA file
- should following the naming convention for VNFs

---

**version**: the version of the virtual network function

This property needs to fulfill following constraints:
- is a string
- should follow semantic versioning

---

**description**: the description for the virtual network function

This property needs to fulfill following constraints:
- is a string

---

**vendor**: the name of vendor of the virtual network function

This property needs to fulfill following constraints:
- is a string

---
