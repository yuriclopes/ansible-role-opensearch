# Ansible Role: OpenSearch

[![Molecule](https://github.com/yuriclopes/ansible-role-opensearch/actions/workflows/ci.yml/badge.svg)](https://github.com/yuriclopes/ansible-role-opensearch/actions/workflows/ci.yml)

Installs and configures Opensearch Cluster on Debian/Ubuntu servers.

## Requirements (Debian)

### APT Packages on Debian target hosts
- iproute2
- python3


* The node role is defined by ansible group. By default `opensearch_master` and `opensearch_data`. Those groups can be changed setting the `ansible_master_group` and `ansible_data_group` respectively.
* Each ansible host must contains the `node_address` variable. This variable will be used to sign the certificates and configure the opensearch.yml file.
* All the nodes must be acessible wich other on port 9200-9300.

```yaml
    - hosts: all
      become: yes
      roles:
        - role: yuriclopes.opensearch
      vars:
        ansible_master_group: opensearch_master
        ansible_data_group: opensearch_data
```

## Role Variables

Additional variables listed below. Available variables are listed in defaults folder (see `defaults/`):

## Dependencies

### PIP Packages (requirements.txt)
- netaddr>=0.7.0

## Example Playbook

```yaml
    - hosts: all
      become: yes
      roles:
        - role: yuriclopes.opensearch
```

## License

MIT / BSD

## Author Information

This role was created in 2022 by Yuri Corona Lopes.