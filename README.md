Role Name
=========

[![Build Status](https://travis-ci.org/HanXHX/ansible-nodejs.svg)](https://travis-ci.org/HanXHX/ansible-nodejs)

Install Node.js and NPM.

Requirements
------------

None

Role Variables
--------------

- `nodejs_upstream`: boolean (default: true), install from upstream repository (version 4.\*)

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: HanXHX.nodejs, nodejs_origin: 'upstream' }

License
-------

GPLv2

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
