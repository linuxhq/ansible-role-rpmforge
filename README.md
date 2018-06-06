# ansible-role-rpmforge

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-rpmforge.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-rpmforge)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-rpmforge-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/rpmforge)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - RepoForge Project

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    rpmforge_arch: "{{ ansible_architecture }}"
    rpmforge_baseurl: "http://repository.it4i.cz/mirrors/repoforge/redhat/el{{ ansible_distribution_major_version }}/en/{{ rpmforge_arch }}/rpmforge/RPMS"
    rpmforge_disable_plugin: []
    rpmforge_disablerepo: []
    rpmforge_dist: "el{{ ansible_distribution_major_version }}.rf"
    rpmforge_enable_plugin: []
    rpmforge_enablerepo: []
    rpmforge_fetch: "{{ rpmforge_baseurl }}/{{ rpmforge_release }}.{{ rpmforge_dist }}.{{ rpmforge_arch }}.rpm"
    rpmforge_packages: []
    rpmforge_pkg: rpmforge-release
    rpmforge_rel: 1
    rpmforge_release: "{{ rpmforge_pkg }}-{{ rpmforge_ver }}-{{ rpmforge_rel }}"
    rpmforge_repository_rpmforge: false
    rpmforge_repository_rpmforge_extras: false
    rpmforge_repository_rpmforge_testing: false
    rpmforge_ver: 0.5.3

All repositories are disabled by default.

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.rpmforge
          rpmforge_disable_plugin:
            - post-transaction-actions
          rpmforge_enablerepo:
            - epel
          rpmforge_packages:
            - unrar            
          rpmforge_repository_rpmforge: true

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
