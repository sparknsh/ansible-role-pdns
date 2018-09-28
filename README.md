# Ansible Role: PowerDNS

#### Version: 1.0.0

[![pipeline status](https://gitlab.com/sparknsh/ansible-role-pdns/badges/master/pipeline.svg)](https://gitlab.com/sparknsh/ansible-role-pdns/commits/master)

Development of this project is managed in a private repository then pushed out to [GitLab](https://gitlab.com/sparknsh/ansible-role-pdns) and [GitHub](https://github.com/sparknsh/ansible-role-pdns) when we have a new version for you. If you have any issues please contact [sparknsh](https://www.sparknsh.com/contact?type=issue&name=ansible-role-pdns)

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
pdns_install_repo: "{{ pdns_auth_powerdns_repo_41 }}"
```

Pick what version of PowerDNS you want to install.

- pdns_auth_powerdns_repo_master
- pdns_auth_powerdns_repo_41
- pdns_auth_powerdns_repo_40

```yaml
pdns_repo_https: True
```
If you want to load the repo over https or not.

```yaml
pdns_config: []

pdns_backends: []
```

#### Example

```yaml
pdns_install_repo: "{{ pdns_auth_powerdns_repo_41 }}"
pdns_repo_https: False
pdns_config:
  local-address: 0.0.0.0
  local-port: 53
  daemon: True
  master: False
  slave: False
  disable-axfr: True

pdns_backends:
  gmysql:
    host: 127.0.0.1
    port: 3306
    user: powerdns
    password: powerdns
    dbname: powerdns
    dnssec: False
```

## Example Playbook

```yaml
- hosts: all
  vars_files:
    - vars/main.yml
  roles:
    - { role: sparknsh.pdns }
```

## License

MIT

## Author Information

This role was created in 2018 by [sparknsh](https://www.sparknsh.com) at [Rebel Media, Inc.](https://www.rebelmedia.io/)
