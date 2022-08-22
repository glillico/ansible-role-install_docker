# ansible-role-install_docker

Installs the Docker CE package.

## Requirements

None.

## Role Variables

    idk_docker_package_name: docker-ce

Defines the package name that will get installed.

## Dependencies

None.

## Issues

The script provided by Docker (https://get.docker.com/) does not currently work correctly on CentOS clones like RockyLinux. 

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
