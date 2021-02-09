gitea_podman
=========

Deploy a simple non-production Gitea instance as a (rootless) container with Podman

Requirements
------------
* Ansible 2.9 and later

Role Variables
--------------

**gitea_user** - User to run the container as

*Default:* `gitea`

**gitea_group** - Group to run the container

*Default:* `gitea`

**gitea_data_dir** - Host path for Gitea data volume

*Default:* `/opt/gitea/data`

**gitea_config_dir** - Host path for Gitea config volume

*Default:* `/opt/gitea/config`

**gitea_container_image** - Container image to use

*Default:* `docker.io/gitea/gitea`

**gitea_container_image_tag** - Container image tag to use

*Default:* `latest-rootless`

**gitea_http_port** - Gitea http listen port

*Default:* `3000`

**gitea_root_url** - Gitea root URL

*Default:* `"http://{{ ansible_default_ipv4.address }}:{{ gitea_http_port }}"`

**gitea_ssh_domain** - Gitea SSH domain

*Default:* `"{{ ansible_default_ipv4.address }}"`

**gitea_ssh_port** - Gitea SSH listen port

*Default:* `2222`

**gitea_manage_firewall_firewalld** - Boolean for role to manage firewall ports with firewalld

*Default:* `true`

Dependencies
------------

collections:
* [containers.podman](https://galaxy.ansible.com/containers/podman)
* [ansible.posix](https://galaxy.ansible.com/ansible/posix)

License
-------

Apache-2.0
