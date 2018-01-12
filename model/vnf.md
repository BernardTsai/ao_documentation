VNF
===

A VNF is a virtualised network function. Its name uniquely identifies it within the context of a model.

The general structure:

```yaml
---
  /{{DN of VNF}}:
    type: tosca.dtag.nodes.VNF
    properties:
      name:        {{name of VNF}}
      version:     {{version of the VNF}}
      state:       {{state of the VNF}}
      description: {{description of the VNF}}
      vendor:      {{vendor of the VNF}}
      public_key:  {{public key to access the VNF}}
```

General Properties
------------------

| Property        | Description                                     |
|-----------------|-------------------------------------------------|
| **type**        | VNF                                             |
| **name**        | unique identifier (4-256 characters)            |
| **version**     | semantic version Vx.y.z                         |
| description     | short description (max 2048 characters)         |
| **state**       | undefined, defined, inactive, active, failure   |
| **vendor**      | name of vendor (4-256 characters)               |
| **public_key**  | public key for SSH access                       |

_required properties are marked in bold_

Remarks
-------

- **fqdn**: `/[VNF name]`
- **name**: a unique name for each VNF merely consisting of alphabetical characters and possibly digits with a length between 8 and 256 characters

Example:
--------

```yaml
---
  ...
  /Clearwater:
    type: tosca.dtag.nodes.VNF
    properties:
      name:        Clearwater
      version:     V0.1.0
      state:       active
      description: Metaswitch Clearwater IMS core
      vendor:      Metaswitch
      public_key:  "ssh-rsa AAAAB3NzaC1yc... Example SSH Keypair"
  ...
```
