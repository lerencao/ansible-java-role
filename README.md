# Ansible Role: Java

## Requirements

None.

## Role Variables

1. jdk_version: 8u31[defalut]
2. install_dir: ~[default]

## Dependencies

None.

## Example Playbook

    - hosts: your-servers
      roles:
        - { role: lerencao.java }

    - hosts: your-servers
      roles:
        - { role: lerencao.java, jdk_version: 8u31 }

    - hosts: your-servers
      roles:
        - { role: lerencao.java, install_dir: /usr/local }

    - hosts: your-servers
      roles:
        - { role: lerencao.java, jdk_version: 8u31, install_dir: /usr/local }

## License

MIT

### Author Information

This role was created by [Jiafeng Cao](https://github.com/lerencao).
