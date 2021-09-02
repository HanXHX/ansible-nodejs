NodeJS Ansible role
===================

 [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-HanXHX.nodejs-blue.svg)](https://galaxy.ansible.com/HanXHX/nodejs/) [![Build Status](https://travis-ci.org/HanXHX/ansible-nodejs.svg)](https://travis-ci.org/HanXHX/ansible-nodejs)

Install Node.js and NPM.

Managed OS
----------

| OS                   | Working  | Active support |
|:--------------------:|:--------:|:--------------:|
| Debian Jessie (8)    | :x:      | :heavy_check_mark: Check latest supported version ([1.2.0](https://github.com/HanXHX/ansible-nodejs/releases/tag/1.2.0)) |
| Debian Stretch (9)   | :x:      | :heavy_check_mark: Check latest supported version ([1.2.0](https://github.com/HanXHX/ansible-nodejs/releases/tag/1.2.0)) |
| Debian Buster (10)   | :x:      | :x:            |


Role Variables
--------------

- `nodejs_upstream`: boolean (default: true), install from upstream repository
- `nodejs_upstream_src`: boolean (default: false), add upstream src (apt) repository
- `nodejs_upstream_version`: integer (default: 10)

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: HanXHX.nodejs }

License
-------

GPLv2

Author Information
------------------

- Twitter: [@hanxhx_](https://twitter.com/hanxhx_)
