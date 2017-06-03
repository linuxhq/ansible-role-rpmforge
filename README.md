# ansible-role-rpmforge

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-rpmforge.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-rpmforge)

RHEL/CentOS - RepoForge Project

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    rpmforge_pkg: rpmforge-release
    rpmforge_ver: 0.5.3
    rpmforge_rel: 1
    rpmforge_arch: "{{ ansible_architecture }}"
    rpmforge_dist: "el{{ ansible_distribution_major_version }}.rf"
    rpmforge_baseurl: "http://pkgs.repoforge.org/{{ rpmforge_pkg }}"
    rpmforge_release: "{{ rpmforge_pkg }}-{{ rpmforge_ver }}-{{ rpmforge_rel }}"
    rpmforge_fetch: "{{ rpmforge_baseurl }}/{{ rpmforge_release }}.{{ rpmforge_dist }}.{{ rpmforge_arch }}.rpm"
    rpmforge_rpmforge: False
    rpmforge_rpmforge_extras: False
    rpmforge_rpmforge_testing: False

All repositories are disabled by default.

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.rpmforge
          rpmforge_repos:
            rpmforge: True

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
