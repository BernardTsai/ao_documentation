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
      vnf:          __VNF__
      tenant:       __TENANT__
      placement:    __PLACEMENT__
      flavor:       __FLAVOR__
      image:        __IMAGE__
      sizing:       {min: __MINSIZE__ max: __MAXSIZE__, size: __SIZE__}
      volumes:
        - {device: __VOLUME_DEVICE__, name: __VOLUME_NAME__, size: __VOLUME_SIZE__, mount: __VOLUME_MOUNT__}
        - ...
      interfaces:
        - network:  __INTERFACE_NETWORK__
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

- **fqdn**: `/[VNF name]/[Tenant name]/[Component name]`
- **name**: a unique name within VNF and tenant context merely consisting of alphabetical characters and possibly digits with a length between 4 and 256 characters


Example
-------

```yaml
  ...
  /Clearwater/cloud/jumphost:
    type: InternalComponent
    properties:
      name:         jumphost
      version:      V1.0.0
      state:        started
      description:  Jumphost server
      vnf:          Clearwater
      tenant:       cloud
      placement:    MGMT
      flavor:       m1.small
      image:        ubuntu-16.04.1-x86_64
      sizing:       {min: 1, max: 1, size: 1}
      interfaces:
        - network:    svc2
        - network:    oam
        - ...
      services:
        - name:    ssh
          network: svc2
          ports:
            - { protocol: tcp, min: 22, max: 22 }
        - ...
      dependencies:
        - {service: /Clearwater/cloud/sprout/ssh, network: oam}
        - ...
  ...
```
