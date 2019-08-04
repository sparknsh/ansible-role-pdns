# Ansible Role: PowerDNS

#### Version: 1.2.0

[![](https://img.shields.io/badge/role-sparknsh.pdns-blue.svg)](https://galaxy.ansible.com/sparknsh/pdns)

Development of this project is managed in a private repository then pushed out to [GitLab](https://gitlab.com/sparknsh/ansible-role-pdns) and [GitHub](https://github.com/sparknsh/ansible-role-pdns) when we have a new version for you. If you have any issues please contact [sparknsh](https://www.sparknsh.com/contact?type=issue&name=ansible-role-pdns)

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
pdns__install_repo: "{{ pdns__auth_powerdns_repo_42 }}"
```

Pick what version of PowerDNS you want to install.

- pdns__auth_powerdns_repo_master
- pdns__auth_powerdns_repo_42
- pdns__auth_powerdns_repo_41
- pdns__auth_powerdns_repo_40

```yaml
pdns__repo_https: True
```
If you want to load the repo over https or not.

```yaml
pdns__config: []

pdns__backends: []
```

#### Example

```yaml
pdns__install_repo: "{{ pdns__auth_powerdns_repo_42 }}"
pdns__repo_https: false
pdns__config:
  local-address: 0.0.0.0
  local-port: 53
  daemon: true
  master: false
  slave: false
  disable-axfr: true

pdns__backends:
  gmysql:
    host: 127.0.0.1
    port: 3306
    user: powerdns
    password: powerdns
    dbname: powerdns
    dnssec: false
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
