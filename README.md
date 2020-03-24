inmotionhosting.redis
=========

Modular Ansible Role for deploying and configuring Redis

[![Build Status](https://travis-ci.org/inmotionhosting/ansible-role-redis.png?branch=master)](https://travis-ci.org/inmotionhosting/ansible-role-redis)

Requirements
------------

* CentOS 7.x or later
* Debian 8 or later
* Ubuntu 16.04 LTS or later

Role Variables
--------------

| Variable | Definition |
| -------- | ---------- |
| redis_conf | The location of the Redis configuration file.
| redis_conf_bind | The IP addresses Redis will bind to.
| redis_conf_daemonize | Whether Redis should run as a daemon.
| redis_conf_logfile | The location of the Redis log file.
| redis_conf_maxmemory | The maximum memory to be used by Redis.
| redis_conf_maxmemory_policy | The memory handling policy to use.
| redis_conf_pidfile | The location of the Redis pidfile.
| redis_conf_requirepass | Whether a password is required to log in to Redis.
| redis_conf_supervised | The init system Redis should target. <br><br>Default: `systemd`
| redis_conf_timeout | The maximum time a client connection to Redis should live.
| redis_conf_unixsocket | Whether Redis should be configured to use a unix socket.
| redis_conf_unixsocket_location | The location of the Redis unix socket file.
| redis_conf_unixsocket_permissions | The unix permissions to set on the unix socket file.
| redis_daemon | The name of the Redis daemon.
| redis_packages | The packages needed by this role.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: inmotionhosting.redis

License
-------

GPLv3

Author Information
------------------

[InMotion Hosting](https://inmotionhosting.com)
