# Internal Component

An internal component describes a cluster of compute nodes residing within a virtual datacenter.
Its name in combination with the name of the VNF and the name of the tenant to which it belongs uniquely identifies it within the context of a model.

The general structure:

```yaml
  ...
  __FQDN__:
    type: InternalComponent
    properties:
      name:         __NAME__
      version:      __VERSION__
      state:        __STATE__
      description:  __DESCRIPTION__
      network:      __NETWORK__
      ipv4:
        - __IPV4_CIDR__
        - ...
      ipv6:
        - __IPV6_CIDR__
        - ...
      services:
        - name:    __SERVICE_NAME__
          network: __SERVICE_NETWORK__
          ports:
            - { protocol: __PORT_PROTOCOL__, min: __PORT_MIN__, max: __PORT_MAX__ }
        - ...
      dependencies:
        - {service: __DEPENDENCY__, network: __DEPENDENCY_NETWORK__}
        - ...
  ...
```

General Properties
------------------

| Property           | Description                                     |
|--------------------|-------------------------------------------------|
| **type**           | InternalComponent                               |
| **name**           | unique identifier (4-256 characters)            |
| **version**        | semantic version Vx.y.z                         |
| description        | short description (max 2048 characters)         |
| **state**          | undefined, defined, inactive, active, failure   |
| **vnf**            | name of VNF (4-256 characters)                  |
| **tenant**         | name of tenant (4-256 characters)               |
| **placement**      | EXT, INT or MGMT                                |
| **flavor**         | name of flavor (string)                         |
| **image**          | name of the OS image (string)                   |

Sizing properties
-----------------

| Property           | Description                                     |
|--------------------|-------------------------------------------------|
| **min**            | min. size of cluster (positive integer)         |
| **max**            | max. size of cluster (positive integer)         |
| **size**           | def. size of cluster (positive integer)         |

Volume Properties<a name="1"></a>
-----------------

| Property         | Description                                     |
|------------------|-------------------------------------------------|
| **device**       | device name (string)                            |
| **size**         | size of volume in GB (positive integer)         |
| **type**         | filesystem type (string)                        |
| **mount**        | mount point (string)                            |

Interface Properties<a name="2"></a>
--------------------

| Property         | Description                                     |
|------------------|-------------------------------------------------|
| **network**      | uuid of network (string)                        |
| type             | left, right, mgmt                               |
| ipv4_fixed       | list of IPv4 addresses (string)                 |
| ipv4_allowed     | list of IPv4 addresses (string)                 |
| ipv6_fixed       | list of IPv6 addresses (string)                 |
| ipv6_allowed     | list of IPv6 addresses (string)                 |

dependencies Properties<a name="3"></a>
-----------------------

| Property         | Description                                     |
|------------------|-------------------------------------------------|
| **component**    | uuid of internal or external component (string) |
| **capability**   | name of capability (string)                     |
| **network**      | uuid of network (string)                        |

Services Properties<a name="4"></a>
-------------------

| Property            | Description                                     |
|---------------------|-------------------------------------------------|
| **name**            | name of capability (string)                     |
| **network**         | uuid of network (string)                        |
| [**endpoints**](#5) | list of endpoint properties                     |

Endpoint Properties<a name="5"></a>
-------------------

| Property         | Description                                     |
|------------------|-------------------------------------------------|
| **protocol**     | tcp, udp, ...                                   |
| **min**          | integer between 1 and 65535                     |
| **max**          | integer between 1 and 65535 (larger than min)   |

_required properties are marked in bold_

Remarks
-------

- **fqdn**: `/[Component name]`
- **name**: a unique name within VNF and tenant context merely consisting of alphabetical characters and possibly digits with a length between 4 and 256 characters


Example
-------

```yaml
  ...
  /administrators:
    type: ExternalComponent
    properties:
      name:        administrators
      version:     V1.0.0
      state:       started
      description: Tenant administrator
      ipv4:
        - 0.0.0.0/0
      dependencies:
        - {service: /Clearwater/cloud/jumphost/ssh,  network: /Clearwater/cloud/svc2}
  ...
```
