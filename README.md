![Ansible Molecule Pipeline](https://github.com/inmotionhosting/ansible-role-redis/actions/workflows/main.yml/badge.svg) [![GPL-3.0 License](https://img.shields.io/github/license/inmotionhosting/ansible-role-redis.svg?color=blue)](https://github.com/inmotionhosting/ansible-role-redis/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/inmotionhosting/ansible-role-redis.svg)](https://github.com/inmotionhosting/ansible-role-redis/stargazers)

![InMotion Hosting Ultrastack](https://www.inmotionhosting.com/wp-content/uploads/2024/01/ultrastack-logo-black-vertical.png)

# Ansible Role: Redis

Modular Ansible Role for deploying and configuring Redis

## Requirements

This role supports the following platforms:

- **RHEL/CentOS/AlmaLinux/RockyLinux**: 7, 8, 9
- **Debian**: 12 (Bookworm), 13 (Trixie)
- **Ubuntu**: 22.04 (Jammy), 24.04 (Noble)

## Package Sources

This role installs Redis from the following repositories:

- **CentOS/RHEL 7**: [Remi Repository](https://rpms.remirepo.net/)
- **RHEL/CentOS/AlmaLinux/RockyLinux 8+**: [Official Redis Repository](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/rpm/)
- **Debian/Ubuntu**: [Official Redis Repository](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/linux/)

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
| `redis_conf_io_threads` | `(CPU cores - 1)` | Number of I/O threads for threaded I/O (minimum 1). |
| `redis_conf_lazyfree_lazy_eviction` | `yes` | Use lazy freeing on eviction (improves performance). |
| `redis_conf_lazyfree_lazy_expire` | `yes` | Use lazy freeing on key expiration (improves performance). |
| `redis_conf_lazyfree_lazy_server_del` | `yes` | Use lazy freeing on server-side DEL operations (improves performance). |
| `redis_conf_replica_lazy_flush` | `yes` | Use lazy freeing on replica FLUSHALL/FLUSHDB (improves performance). |
| `redis_conf_maxmemory` | `""` | Maximum memory limit (e.g., 1G, 512M). Empty for no limit. |
| `redis_conf_maxmemory_policy` | `allkeys-lru` | The memory eviction policy to use. |
| `redis_conf_port` | `6379` | The port Redis will listen on. |
| `redis_conf_requirepass` | `false` | The password required to authenticate to Redis, or `false` to disable authentication. |
| `redis_conf_timeout` | `60` | Client idle timeout in seconds (0 to disable). |
| `redis_conf_unixsocket_path` | `""` | Path to the Redis Unix socket file (empty to disable). |
| `redis_conf_unixsocket_permissions` | `770` | The permissions to set on the Unix socket file. |

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
