# Role Name: GOLANG

[![Build Status](https://travis-ci.org/deluxebrain/ansible-role-golang.svg?branch=master)](https://travis-ci.org/deluxebrain/ansible-role-golang)

Golang installer for Linux.

## Requirements

None.

## Role Variables

All of the listed variables are defined in `defaults/main.yml`.
Individual variables can be set or overridden by setting them in a playbook for this role.

- `golang_version`: ( default: latest )
  - Golang version to install
- `golang_install_dir`: ( default : /usr/local )
  - Golang installation directory
- `go_path`: ( default unset )
  - Set to override default workspace directory

## Dependencies

None.

## Example Playbook

Example below for the following:

- Installation of specific version of golang

```yaml
- hosts: all

  roles:
    - role: ansible-role-golang
      golang_version: 1.13.8
```

## License

MIT / BSD

## Author Information

This role was created in 2020 by [deluxebrain](https://www.deluxebrain.com/).
