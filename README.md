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
      golang_version: "1.13.8"
```

## Development Installation

Packages are split into development and production dependencies, which are managed through the included files `requirements-dev.txt` and `requirements.txt` respectively.

Production packages are managed through the `pip-tools` suite, which installs and synchronizes the project dependencies through the included `requirements.in` file.

```sh
# Create project virtual environment
# Install development dependencies into virtual environment
make install
```

`pip-tools` is responsible for the generation of the `requirements.txt` which is a fully pinned requirements file used for both synchronizing the Python virtual environment and for the installation of packages within a production environment.

Note that this means that the `requirements.txt` file *should not be manually edited* and must be regenerated every time the `requirements.in` file is changed. This is done as follows, which also synchronizes any package changes into the virtual environment:

```sh
# Compile the requirements.in file to requirements.txt
# Install the requirements.txt pacakges into the virtual environment
make sync
```

`pip-tools` and other development requirements are installed through the `requirements-dev.txt` file, as follows:

## License

MIT / BSD

## Author Information

This role was created in 2020 by [deluxebrain](https://www.deluxebrain.com/).
