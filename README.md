![Ansible Molecule Pipeline](https://github.com/inmotionhosting/ansible-role-redis/actions/workflows/main.yml/badge.svg) [![GPL-3.0 License](https://img.shields.io/github/license/inmotionhosting/ansible-role-redis.svg?color=blue)](https://github.com/inmotionhosting/ansible-role-redis/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/inmotionhosting/ansible-role-redis.svg)](https://github.com/inmotionhosting/ansible-role-redis/stargazers)

![InMotion Hosting Ultrastack](https://www.inmotionhosting.com/wp-content/uploads/2024/01/ultrastack-logo-black-vertical.png)

# Ansible Role: Redis

Modular Ansible Role for deploying and configuring Redis

## Requirements

This role supports the following platforms:

- **RHEL/CentOS/AlmaLinux/RockyLinux**: 8, 9
- **Debian**: 12 (Bookworm), 13 (Trixie)
- **Ubuntu**: 22.04 (Jammy), 24.04 (Noble)

## Package Sources

This role installs Redis from the official Redis repository to provide the latest stable versions:

- **RHEL/CentOS/AlmaLinux/RockyLinux**: [https://packages.redis.io/rpm/](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/rpm/)
- **Debian/Ubuntu**: [https://packages.redis.io/deb/](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/linux/)

## Installation

```bash
ansible-galaxy install inmotionhosting.redis
```

## Dependencies

None.

## Role Variables

Available variables are listed below with their default values (see `defaults/main.yml`):

| Variable | Default | Description |
| -------- | ------- | ----------- |
| `redis_conf_bind` | `127.0.0.1` | The IP addresses Redis will bind to. |
| `redis_conf_daemonize` | `yes` | Whether Redis should run as a daemon. |
| `redis_conf_logfile` | `/var/log/redis/redis.log` | The location of the Redis log file. |
| `redis_conf_maxmemory` | `1G` | The maximum memory to be used by Redis. |
| `redis_conf_maxmemory_policy` | `allkeys-lru` | The memory eviction policy to use. |
| `redis_conf_pidfile` | `/run/redis/redis-server.pid` | The location of the Redis pidfile. |
| `redis_conf_port` | `6379` | The port Redis will listen on. |
| `redis_conf_requirepass` | `false` | The password required to authenticate to Redis, or `false` to disable authentication. |
| `redis_conf_supervised` | `systemd` | The init system Redis should notify. |
| `redis_conf_timeout` | `60` | Client idle timeout in seconds (0 to disable). |
| `redis_conf_unixsocket` | `true` | Whether to enable Unix socket connections. |
| `redis_conf_unixsocket_location` | `/var/run/redis/redis.sock` | The location of the Redis Unix socket file. |
| `redis_conf_unixsocket_permissions` | `770` | The permissions to set on the Unix socket file. |
| `redis_package` | `redis` | The Redis package name to install. |
| `redis_systemd_restart` | `false` | Whether to configure systemd restart behavior. |
| `systemd_restart_setting` | `on-failure` | The systemd restart policy (`no`, `on-success`, `on-failure`, `on-abnormal`, `on-watchdog`, `on-abort`, `always`). |

## Example Playbook

Basic usage:

```yaml
- hosts: www
  roles:
    - role: inmotionhosting.redis
```

With custom configuration:

```yaml
- hosts: www
  roles:
    - role: inmotionhosting.redis
      redis_conf_maxmemory: 2G
      redis_conf_requirepass: "your_secure_password"
      redis_conf_bind: "0.0.0.0"
```

## License

GPLv3

## Author Information

[InMotion Hosting](https://inmotionhosting.com)
