![Ansible Lint](https://github.com/johanneskastl/ansible-role-create_caasp_skuba_bootstrap_script/workflows/Ansible%20Lint/badge.svg)

create_caasp_skuba_bootstrap_script
=========

Create a bootstrap script to set up a kubernetes cluster with skuba, pre-filled matching your environment.

Requirements
------------

The ansible groups must be as follows:
- `first_master_node`: contains the first master node, that will be used to bootstrap the cluster
- `master_nodes`: contains all master nodes, including the first one
- `worker_nodes`: contains all kubernetes worker nodes (i.e. not master nodes)

`hostvars[groups['first_master_node'][0]].external_ip` contains the external (floating) IP, i.e. this needs to be defined as a host_var for the first master.

Role Variables
--------------

`domain_name`: Specify the domain part of the FQDN.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: 'johanneskastl.create_caasp_skuba_bootstrap_script'
           domain_name: 'example.org'

License
-------

BSD-3-Clause

Author Information
------------------

I am Johannes Kastl, reachable via kastl@b1-systems.de.
