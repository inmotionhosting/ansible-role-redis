![Ansible Molecule Pipeline](https://github.com/inmotionhosting/ansible-role-redis/actions/workflows/main.yml/badge.svg) [![GPL-3.0 License](https://img.shields.io/github/license/inmotionhosting/ansible-role-redis.svg?color=blue)](https://github.com/inmotionhosting/ansible-role-redis/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/inmotionhosting/ansible-role-redis.svg)](https://github.com/inmotionhosting/ansible-role-redis/stargazers)

![InMotion Hosting Ultrastack](https://www.inmotionhosting.com/wp-content/uploads/2024/01/ultrastack-logo-black-vertical.png)

# Ansible Role: Redis

Modular Ansible Role for deploying and configuring Redis

## Requirements
This Ansible role supports the two latest stable releases of specific
server-focused Linux distributions and aims to follow their deprecation
policies. Additionally we will focus on supporting the latest two stable
releases of each, which at the time of writing are as follows:

* CentOS 7.x
* Debian 10 or later
* Ubuntu 20.04 LTS or later
* AlmaLinux 8.x or later
* RockyLinux 8.x or later

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
| redis_conf_port | Accept connections on the specified port.
| redis_conf_requirepass | Whether a password is required to log in to Redis.
| redis_conf_supervised | The init system Redis should target. <br><br>Default: `systemd`
| redis_conf_timeout | The maximum time a client connection to Redis should live.
| redis_conf_unixsocket | Whether Redis should be configured to use a unix socket.
| redis_conf_unixsocket_location | The location of the Redis unix socket file.
| redis_conf_unixsocket_permissions | The unix permissions to set on the unix socket file.
| redis_daemon | The name of the Redis daemon.

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
