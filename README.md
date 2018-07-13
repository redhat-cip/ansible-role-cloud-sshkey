# Ansible Cloud: SSH Key role

An Ansible role for managing SSH keys on the Cloud in an agnostic cloud provider way.

This role is part of the [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) broader effort.

## Pre-requisites

Please refer to [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) [README.md](https://github.com/redhat-cip/ansible-cloud/blob/master/README.md) to see how to configure your system the proper way for the provide you wish to use.


## Role Variables

| Variable name        | Required  | Default | Type   | Description                   |
|----------------------|-----------|---------|--------|-------------------------------|
| cloud_sshkey_name    | True      | N/A     | String | Name of the SSH keya          |
| cloud_sshkey_content | True      | N/A     | String | Content of the SSH key        |
| cloud_sshkey_state   | False     | present | String | Should the SSK key be present |


## Example

```
---
- hosts: localhost
  vars:
    ansible_cloud_provider: vultr
  tasks:
    - name: Create SSH key
      include_role:
        name: cloud-sshkey
      vars:
        cloud_sshkey_name: 'ansiblecloud-testkey'
        cloud_sshkey_content: 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC+ZFQv3MyjtL1BMpSA0o0gIkzLVVC711rthT29hBNeORdNowQ7FSvVWUdAbTq00U7Xzak1ANIYLJyn+0r7olsdG4XEiUR0dqgC99kbT/QhY5mLe5lpl7JUjW9ctn00hNmt+TswpatCKWPNwdeAJT2ERynZaqPobENgvewrewqdsaqdwqrewqrewqfdsqfeEUr2Cdq7Nb7U0XFXh3x1p0v0+MbL4tiJwPlMAGvFTKIMt+EaA+AsRIxiOo9CMk5ZuOl9pT8h5vNuEOcvS0qx4v44EAD2VOsCVCcrPNMcpuSzZP8dRTGU9wRREAWXngD0Zq9YJMH38VTxHiskoBw1NnPz me@home'
```


## License

Apache 2.0


## Authors Information

  - Ricardo Carrillo Cruz <ricarril@redhat.com>
  - Yanis Guenane <yguenane@redhat.com>
