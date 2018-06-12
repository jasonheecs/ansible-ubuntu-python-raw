Ansible Role: Install Python on Ubuntu machines that do not have Python pre-installed
=========
[![Build Status][travis-badge]][travis-link]
[![Galaxy Role][role-badge]][galaxy-link]

An ansible role that gets Ansible to work on bare Ubuntu machines that do not have Python pre-installed. It checks if python is installed, if not, it installs it via the [raw](https://docs.ansible.com/ansible/latest/modules/raw_module.html) module.

Requirements
------------

None.


Installation
------------
`ansible-galaxy install jasonheecs.ubuntu-python-raw`


Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

```yaml
python_version: 3
```

Dependencies
------------

None


Example Playbook
----------------

```yaml
- name: Setup
  hosts: all
  become: yes
  gather_facts: false # You must disable the gather of facts for this role to work as intended
  roles:
    - { role: jasonheecs.ubuntu-python-raw }
```


Tests
---------------
Testing is done via [Test Kitchen](https://github.com/test-kitchen/test-kitchen), [Kitchen Ansible](https://github.com/neillturner/kitchen-ansible) and [Kitchen Docker](https://github.com/test-kitchen/kitchen-docker)

To run the tests, make sure [Ruby](https://www.ruby-lang.org/en/documentation/installation/) and [Docker](https://docs.docker.com/installation/#installation) are installed and run the following:

```
gem install bundler && bundle exec kitchen test
```

Refer to the [travis.yml](.travis.yml) file and [Travis build logs][travis-link] for details on the test build process and expected outputs.


Supported Platforms
-------
This ansible role has been tested against the following platforms:
- Ubuntu 18.04
- Ubuntu 16.04
- Ubuntu 14.04

License
-------

MIT


Author Information
------------------

[Jason Hee](https://jasonhee.com)

[galaxy-link]: https://galaxy.ansible.com/jasonheecs/ubuntu-python-raw/
[role-badge]: https://img.shields.io/ansible/role/26273.svg
[travis-badge]: https://travis-ci.com/jasonheecs/ansible-ubuntu-python-raw.svg?branch=master
[travis-link]: https://travis-ci.com/jasonheecs/ansible-ubuntu-python-raw