Ansible Role: HAProxy
=========

HAProxy installation for Linux.

Requirements
------------

TO BE ADDED

Role Variables
--------------

| Variable                 | usage                                            |
| ------------------------ | ------------------------------------------------ |
| `compile_from_source`    | Wether to compile HAProxy from source or not     |
| `haproxy_version`        | HAProxy versions (e.g. `3.0`, `2.8`)             |
| `haproxy_patch_version`  | HAProxy patch version                            |
| `haproxy_download_url`   | Tarball archive URL                              |
| `haproxy_download_dest`  | Location to store download archive               |
| `haproxy_checksum_alg`   | HAProxy tarball archive check sum algorithm      |
| `haproxy_checksum_value` | HAProxy tarball archive check sum value          |
| `haproxy_unarchive_dest` | Location to extract HAProxy tarball archive into |
| `haproxy_user`           | HAProxy user                                     |
| `haproxy_group`          | HAProxy group                                    |
| `haproxy_user_home_dir`  | HAProxy user home directory                      |
| `haproxy_conf_dir`       | HAProxy configuration directory                  |
| `haproxy_runtime_dir`    | HAProxy runtime directory                        |

Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      gather_facts: false
      tasks:

        - name: Setup
          ansible.builtin.setup:
            gather_subset:
              - '!all'
              - '!min'
              - 'distribution'

        - name: Include AnwarYagoub.haproxy role
          ansible.builtin.include_role:
            name: AnwarYagoub.haproxy

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2024 by [Anwar Yagoub](https://github.com/AnwarYagoub)