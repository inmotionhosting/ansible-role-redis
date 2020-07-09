[![Build Status](https://travis-ci.org/inmotionhosting/ansible-role-redis.png?branch=master)](https://travis-ci.org/inmotionhosting/ansible-role-redis) [![GPL-3.0 License](https://img.shields.io/github/license/inmotionhosting/ansible-role-redis.svg?color=blue)](https://github.com/inmotionhosting/ansible-role-redis/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/inmotionhosting/ansible-role-redis.svg)](https://github.com/inmotionhosting/ansible-role-redis/stargazers)

# Ansible Role: Redis

Modular Ansible Role for deploying and configuring Redis

## Requirements

* CentOS 7.x or later
* Debian 9 or later
* Ubuntu 16.04 LTS or later

## Dependencies

None.

## Role Variables

Available variables are listed below with their default values (you can also see `defaults/main.yml`)

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

## Example Playbook

```yaml
- hosts: www
  roles:
    - role: inmotionhosting.redis
```

## License

GPLv3

## Author Information

[InMotion Hosting](https://inmotionhosting.com)
