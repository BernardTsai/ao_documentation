Usage
=====

These playbooks manage the lifecycle of virtual network functions in an OpenStack cloud environment via ansible in a standardized manner.

Access to cloud API endpoints is defined
via the "configurations/clouds.yml" file
which is encrypted via ansible-vault.

The playbooks take the name of VNF as a paramater/variable as shown in the examples below.

The VNF specific requirements are kept in
variables file which will be downloaded from a repository in the course of the process.

Prerequisites:
--------------

* ansible
* git
* clone this repoitory
* access to an OpenStack API endpoint (configurations are kept in clouds.yaml in the configurations sub-directory)
* a cloud configuration file 'cloud.yml'
* a VNF descriptor stored at:

  https://raw.githubusercontent.com/BernardTsai/applications/master/{{vnf}}/descriptor.yml"
* a VNF cluster descriptor stored at:

  https://raw.githubusercontent.com/BernardTsai/applications/master/{{vnf}}/{{cluster}}descriptor.yml"


Inventory:
----------

Determine the current setup of a tenant:

    ansible-playbook inventory-playbook.yml --extra-vars "@cloud.yml" --extra-vars "vnf=Clearwater"

The output will be pushed to the repository:

  https://raw.githubusercontent.com/BernardTsai/applications/master/inventory/{{timestamp}}.yml"


Deployment:
-----------

Create/update a tenant:

    ansible-playbook deployment-playbook.yml --extra-vars "@cloud.yml" --extra-vars "vnf=Clearwater"

Scale-Out:
----------

Scale-out a cluster of a VNF (e.g. ellis):

    ansible-playbook scale-out-playbook.yml --extra-vars "@cloud.yml" --extra-vars "vnf=Clearwater cluster=ellis"

Scale-In:
---------

Scale-in a cluster node of a VNF (e.g. node 0 of ellis):

    ansible-playbook scale-in-playbook.yml --extra-vars "@cloud.yml" --extra-vars "vnf=Clearwater cluster=ellis node=0"

Cleanup
----------

Destroy the virtual resources of an existing tenant (tenant and administrator will remain):

    ansible-playbook cleanup-playbook.yml --extra-vars "@cloud.yml" --extra-vars "vnf=Clearwater"
