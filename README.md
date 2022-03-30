# VM Customisation
This collection of roles is able to customise VM's based on their environment, role and zone.

It aims to replicate the workflow of hiera using the idea of a "common", "role" and "environment" setup with seperate variables for each section.

## The workflow
The idea behind this is to identify three area's of configuration for our node.

  * "common" configuration, users, ssh_keys, filesystems, NFS mounts, etc.
  * Next we identify the "role" specific configuration including application packages, users, ssh_keys, NFS mounts, ulimits, kernel settings, etc
  * Finally, we take the "environment" specific configuration and apply that.

All of the above need to work with all environment levels from test, AT and production.


