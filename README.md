# Ansible Role : install_docker

[![CI](https://github.com/glillico/ansible-role-install_docker/workflows/CI/badge.svg)](https://github.com/glillico/ansible-role-install_docker/actions?query=workflow%3ACI)

Installs the Docker CE package.

## Requirements

None.

## Role Variables

### defaults/main.yml

|Variable|Description|
|---|:---|
|idk_docker_package_name|Defines the package name that will be installed.|
|idk_docker_add_to_group|Defines whether the task to add userdis to the `docker` group should be run.|
|idk_docker_group_users|Defines the users that will be added to the `docker` group.|

## Dependencies

The `python3-apt` package must either be installed or be available to be installed on Debain 10 & 11 based system.

These against the vagrant VM's produced by [Jeff Geerling](https://app.vagrantup.com/geerlingguy/).

## Issues

The script provided by Docker (https://get.docker.com/).

- Is no longer suported on Debian 9.
- Does not currently work on clones such as RockyLinux or AlmaLinux.

### CentOS 8 Repositories

Due to CentOS Linux 8 going End Of Life (EOL) as of December 31st 2021, You will need to run the below commands on the server to allow the yum/dnf commands to work as expected.

```
$ cd /etc/yum.repos.d/
$ sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
$ sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
$ yum check-update
```

## Example Playbook

    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
        - glillico.install_docker

## License

MIT

## Author Information

This project/role was created in 2022 by Graham Lillico.
