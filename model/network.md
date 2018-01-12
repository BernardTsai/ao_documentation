# Network

A network describes a tenant specific routing network.
Its name in combination with the name of the VNF and the name of the tenant uniquely identifies it within the context of a model.

The general structure:

```yaml
  ...
  /{{DN VNF}}/{{DN tenant}}/{{DN network}}:
    type: Network
    properties:
      name:        {{name of network}}
      version:     {{version of network}}
      state:       {{state of network}}
      description: {{description of network}}
      vnf:         {{dn of VNF}}
      tenant:      {{dn of tenant}}
      ipv4:
        cidr:       {{IPv4 cidr}}
        gateway:    {{IPv4 gateway}}
        start:      {{IPv4 start of IP pool}}
        end:        {{IPv4 end of IP pool}}
      ipv6:
        cidr:       {{IPv6 cidr}}
        gateway:    {{IPv6 gateway}}
        start:      {{IPv6 start of IP pool}}
        end:        {{IPv6 end of IP pool}}
  ...
```

General Properties
------------------

| Property         | Description                                     |
|------------------|-------------------------------------------------|
| **type**         | Network                                         |
| **name**         | unique identifier (4-256 characters)            |
| **version**      | semantic version Vx.y.z                         |
| description      | short description (max 2048 characters)         |
| **state**        | undefined, defined, inactive, active, failure   |
| **vnf**          | dn of VNF (4-256 characters)                    |
| **tenant**       | dn of tenant (4-256 characters)                 |

IPv4/IPv7 Properties
--------------------

| Property        | Description                                     |
|-----------------|-------------------------------------------------|
| **cidr**        | network range                                   |
| **gateway**     | gateway IP address                              |
| **start**       | start of IP address pool                        |
| **end**         | end of IP address poll                          |

_required properties are marked in bold_

Remarks
-------

- **fqdn**: `/[VNF name]/[Tenant name]/[Network name]`
- **name**: a unique name within the VNF and tenant context merely consisting of alphabetical characters and possibly digits with a length between 8 and 256 characters

Example
-------

```yaml
  ...
  /Clearwater/cloud/oam:
    type: tosca.dtag.nodes.Network
    properties:
      name:        oam
      version:     V1.0.0
      state:       active
      description: OAM network (managment )
      vnf:         Clearwater
      tenant:      cloud
      ipv4:
        cidr:       192.168.0.1/24
        gateway:    192.168.0.1
        start:      192.168.0.16
        end:        192.168.0.191
  ...
```
