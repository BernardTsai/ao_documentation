VNF
===

A VNF represents a virtualized network function which may need to be distributed over several datacenters. The node template is structured in the following manner:

<pre>
...
topology_template:
	node_templates:

    ...

		[name of VNF]:
			type: tosca.dtag.nodes.VNF
			properties:
				name:	[name of VNF]
				version: [version of VNF]
				description: [description of VNF]
				vendor:	[name of vendor]

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
