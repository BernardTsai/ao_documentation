# Quick Start

This chapter provides instructions of how to setup the
application orchestrator and manage the lifecycle of a simple VNF. In this case the simple VNF is the Clearwater IMS solution.

## Prerequisites

These are the main prerequisites which need to be met:

* Developer laptop
  * sufficient memory > 8GB
  * internet access
  * ansible installed
  * python3 installed
  * git installed
  * docker engine installed [&#x1F50D;](https://docs.docker.com/engine/installation/)
* Access to an OpenStack cloud (e.g. [TryStack](http://trystack.org/))

## Installation

1. **Create and activate a virtual environment**

  ```
  virtualenv -p python3 lcm
  cd lcm
  source bin/activate
  ```

2. **Install Ansible AWX in Docker**

  Follow the instructions on the Ansible AWX website
  [&#x1F50D;](https://github.com/ansible/awx/blob/devel/INSTALL.md#docker):

    ```
    git clone https://github.com/ansible/awx.git
    cd awx/installer
    ansible-playbook -i inventory install.yml
    ```

    The installation has completed if one can access
    ansible tower by opening a browser with the URL
    "http://localhost" and accessing the
    GUI with username/password: "admin/password".

3. **Clone the LCM repository**

  ```
  cd ../..
  git clone https://github.com/BernardTsai/lcm.git
  cd lcm/installer
  ```

4. **Customize**

5. **Configure**

6. **Deploy VNF**
