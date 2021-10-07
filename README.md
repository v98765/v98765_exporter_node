Role Name: Prometheus node exporter
=========

Deploy and configure [node_exporter](https://github.com/prometheus/node_exporter)

Requirements
------------

Ansible 2.10

Role Variables
--------------

Name | Default Value
---|---
`node_exporter_version` | 1.2.2
`node_exporter_system_user` | "node-exp"
`node_exporter_system_group` | "node-exp"
`node_exporter_install_dir` | "/usr/local/bin"
`node_exporter_textfile_dir` | "/var/lib/node_exporter"
`node_exporter_repo_dir` | "/var/tmp/archive"
`node_exporter_config_dir` | "/etc/node_exporter"
`node_exporter_tls_server_config` | {}
`node_exporter_http_server_config` | {}
`node_exporter_basic_auth_users` | {}


```sh
mkdir -p /var/tmp/archive
cd /var/tmp/archive
wget https://github.com/prometheus/node_exporter/releases/download/v1.2.2/node_exporter-1.2.2.linux-amd64.tar.gz
```

Example Playbook
----------------

```yaml
---
- hosts: vmdb
  gather_facts: true
  connection: ssh
  roles:
    - v98765_exporter_node

```

License
-------

BSD
