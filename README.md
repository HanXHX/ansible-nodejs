NodeJS Ansible role
===================

 [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-HanXHX.nodejs-blue.svg)](https://galaxy.ansible.com/HanXHX/nodejs/) [![Build Status](https://travis-ci.org/HanXHX/ansible-nodejs.svg)](https://travis-ci.org/HanXHX/ansible-nodejs)

Install Node.js and NPM.

Requirements
------------

None

Role Variables
--------------

- `nodejs_upstream`: boolean (default: true), install from upstream repository
- `nodejs_upstream_src`: boolean (default: false), add upstream src (apt) repository
- `nodejs_upstream_version`: integer (default: 6)

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
