# ansible-role-yum

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-yum.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-yum)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-yum-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/yum)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - Yellowdog Updater Modified

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    yum_install: []
    yum_opts:
      allow_downgrade: false
      conf_file: ''
      disable_gpg_check: false
      disablerepo: []
      enablerepo: []
      exclude: ''
      installroot: /
      security: false
      skip_broken: false
      update_cache: false
      validate_certs: true
    yum_permissions: []
    yum_protected:
      systemd:
        - systemd
    yum_remove: []
    yum_update: false

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.yum
          yum_install:
            - bind-utils
            - wget
          yum_opts:
            enablerepo:
              - epel
          yum_permissions:
            - path: /bin/su
              owner: root
              group: root
              mode: 700
          yum_remove:
            - mlocate
          yum_update: true

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
