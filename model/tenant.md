Tenant
======

A tenant represents a virtual datacenter belonging to a virtualised network function.
Its name in combination with the name of the VNF to which it belongs
uniquely identifies it within the context of a model.

The general structure:

```yaml
  ...
  /{{DN VNF}}/{{DN Tenant}}:
    type: Tenant
    properties:
      name:        {{name of tenant}}
      version:     {{version of tenant}}
      state:       {{state of tenant}}
      description: {{description of tenant}}
      vnf:         {{dn of VNF}}
      datacenter:  {{name of data center}}
      flavors:
        - name:        {{name of the flavor}}
          memory:      {{ram size in MB}}
          vcpu:        {{number of vCPUs}}
          disk:        {{size of disk in GB}}
          ephemeral:   {{size of ephemeral disk in GB}}
          swap:        {{size of swap disk in GB}}
          public:      {{flavor is publically available}}
        - ...
  ...
```

General Properties
------------------

| Property        | Description                                     |
|-----------------|-------------------------------------------------|
| **type**        | Tenant                                          |
| **name**        | unique identifier (4-256 characters)            |
| **version**     | semantic version Vx.y.z                         |
| description     | short description (max 2048 characters)         |
| **state**       | undefined, defined, inactive, active, failure   |
| **vnf**         | dn of VNF (4-256 characters)                    |
| **datacenter**  | name of the data center (4-256 characters)      |

Flavor Properties
-----------------

| Property        | Description                                     |
|-----------------|-------------------------------------------------|
| **name**        | name of flavor                                  |
| **memory**      | size of random access memory in MB              |
| **vcpu**        | number of virtual CPUs                          |
| **ephemeral**   | size of ephemeral disk in GB                    |
| **swap**        | size of swap disk in GB                         |
| **public**      | flavor is publically available                  |

_required properties are marked in bold_

Remarks
-------

- **fqdn**: `/[VNF name]/[Tenant name]`
- **name**: a unique name within the VNF context for each tenant merely consisting of alphabetical characters and possibly digits with a length between 4 and 256 characters
- **datacenter**: the name of the datacenter needs to match a name defined in the list of available data centers. This list may be subject to change.

Example
-------

```yaml
  ...
  /Clearwater/cloud:
    type: Tenant
    properties:
      name:        clearwater
      version:     V1.0.0
      state:       started
      description: Clearwater tenant in a cloud data center
      vnf:         Clearwater
      datacenter:  cloud
      flavors:
        - name:        m1.small
          memory:      2048
          disk:        10
          vcpu:        1
          ephemeral:   0
          public:      True
          swap:        0
        - name:        m1.medium
          memory:      4096
          disk:        50
          vcpu:        2
          ephemeral:   0
          public:      True
          swap:        0
  ...
```
