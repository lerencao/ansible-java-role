# Ansible Role: Java

## Requirements

None.

## How it works

When user passes a jdk version, say 8u40, the role goes to load variables corresponding to the version.
(To release user from passing verbose variables used by jdk-downloading, the role limits the supported jdk versions.
If some jdk version is missing, please issue me or pull a request.)
And downlaod jdk package from oracle server to `jdk_download_dir` of the local machine based on these variables.
Then the role unarchives the package to `install_dir` of remote nodes, and do some configurations.
And you're done!

## Role Variables

1. `jdk_version` (defalut: `8u40`): the jdk version you want to install. Only support `8u40` for now.
2. `jdk_download_dir` (default: `/tmp/jdk`): the folder to save jdk package in local machine.
3. `install_dir` (default: `{{ansible_env['HOME']}}`): the path that you want to install the jdk to in remote nodes.

## Dependencies

None.

## Example Playbook

    - hosts: your-servers
      roles:
        - { role: lerencao.java }

    - hosts: your-servers
      roles:
        - { role: lerencao.java, jdk_version: 8u40, jdk_download_dir: /tmp }

    - hosts: your-servers
      sudo: yes
      roles:
        - { role: lerencao.java, install_dir: /usr/local }

    - hosts: your-servers
      sudo:
      roles:
        - { role: lerencao.java, jdk_version: 8u40, install_dir: /usr/local }

## License

MIT

### Author Information

This role was created by [Jiafeng Cao](https://github.com/lerencao).

Special thanks to [silpion/ansible-java](https://github.com/silpion/ansible-java) and [robdyke/ansible-java](https://github.com/robdyke/ansible-java).
