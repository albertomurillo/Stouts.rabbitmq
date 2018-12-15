albertomurillo.rabbitmq
===============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.rabbitmq.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.rabbitmq)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.rabbitmq-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/953)

Ansible role which manage RabbitMQ.
This is a fork from [Stouts.rabbitmq](https://github.com/Stouts/Stouts.rabbitmq)
but installs rabbitmq and erlang from `@centos-openstack-rocky` repository
(Useful when installing rabbitmq and OpenStack on the same node)

#### Variables

```yaml
rabbitmq_enabled: yes

rabbitmq_plugins:                       # Ensure the plugins is installed
  - rabbitmq_management

rabbitmq_users:                         # Ensure the users added
  - user: admin
    password: admin
    vhost: /
    configure_priv: .*
    read_priv: .*
    write_priv: .*
    tags: administrator

rabbitmq_vhosts: []                     # Ensure the vhosts are exists

rabbitmq_users_remove:                  # Ensure the users removed
  - guest
```

#### Usage

Add `albertomurillo.rabbitmq` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - albertomurillo.rabbitmq

  vars:
    rabbitmq_vhosts: [myhost]
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/albertomurillo/ansible-role-rabbitmq/issues)!
