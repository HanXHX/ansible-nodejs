NodeJS Ansible role
===================

 [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-HanXHX.nodejs-blue.svg)](https://galaxy.ansible.com/HanXHX/nodejs/) [![Build Status](https://app.travis-ci.com/HanXHX/ansible-nodejs.svg?branch=master)](https://app.travis-ci.com/HanXHX/ansible-nodejs)

Install Node.js and NPM.

Managed OS
----------

| OS                   |        Working      |    Active support   |
|:--------------------:|:-------------------:|:-------------------:|
| Debian Jessie (8)    | :heavy_check_mark:  | :x: Check latest supported version ([1.2.0](https://github.com/HanXHX/ansible-nodejs/releases/tag/1.2.0)) |
| Debian Stretch (9)   | :heavy_check_mark:  | :x: Check latest supported version ([1.2.0](https://github.com/HanXHX/ansible-nodejs/releases/tag/1.2.0)) |
| Debian Buster (10)   | :heavy_check_mark:  | :heavy_check_mark:  |
| Debian Bullseye (11) | :heavy_check_mark:  | :heavy_check_mark:  |


Role Variables
--------------

- `nodejs_upstream`: boolean (default: true), install from upstream repository
- `nodejs_upstream_src`: boolean (default: false), add upstream src (apt) repository
- `nodejs_upstream_version`: integer (default: 16)

Dependencies
------------

- Ansible >= 2.11
- Collections: community.general

Example Playbook
----------------

    - hosts: servers
      roles:
         - name: HanXHX.nodejs

License
-------

GPLv2


Donation
--------

If this code helped you, or if you’ve used them for your projects, feel free to buy me some :beers:

- Bitcoin: `1BQwhBeszzWbUTyK4aUyq3SRg7rBSHcEQn`
- Ethereum: `0x63abe6b2648fd892816d87a31e3d9d4365a737b5`
- Litecoin: `LeNDw34zQLX84VvhCGADNvHMEgb5QyFXyD`
- Monero: `45wbf7VdQAZS5EWUrPhen7Wo4hy7Pa7c7ZBdaWQSRowtd3CZ5vpVw5nTPphTuqVQrnYZC72FXDYyfP31uJmfSQ6qRXFy3bQ`

No crypto-currency? :star: the project is also a way of saying thank you! :sunglasses:


Author Information
------------------

- Twitter: [@hanxhx_](https://twitter.com/hanxhx_)
