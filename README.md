# VM Customisation
This collection of roles is able to customise VM's based on their environment, role and zone.

It aims to replicate the workflow of hiera using the idea of a "common" (```for Global configuration```), "role" (```for a server role like web or DB```) and "environment" (```for prod/pre-prod & UAT```) setup with seperate variables for each section. You can add more as required.

## The workflow
This diagram visualises the steps that Ansible is running as it goes through the VM customisation workflow.

![Alt text](images/workflow.png?raw=true)

  * "common" configuration is applied first. So users, ssh_keys, filesystems, NFS mounts, etc.
  * Next we identify the "role" specific configuration including application packages, users, ssh_keys, NFS mounts, ulimits, kernel settings, etc
  * Finally, we take the "environment" specific configuration and apply that.

All of the above needs to work with all environment levels from test, AT and production.

## Quick Start
Follow these steps to setup your environment like mine.

  * Clone this repo ```git clone https://github.com/dmccuk/vm_customisation.git```
  * ```cd vm_customisation```
  * Update your hosts/inventory file with the servers you want to run against
  * Make sure your ansible.cfg is setup with your own personal requirements
  * run ansible against your servers: ```ansible-playbook -i hosts.ini vm_customisation.yml```

If you don't have SSH-KEYS, or you need to provide a password to elivate your access, make sure to add one or all of the following: ```-kbK```


