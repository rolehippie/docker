# workspace

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/docker)
[![General Workflow](https://github.com/rolehippie/docker/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/docker/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/docker/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/docker/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/docker/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/docker/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/docker)](https://github.com/rolehippie/docker/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.docker-blue)](https://galaxy.ansible.com/rolehippie/docker)

Ansible role to install and configure Docker container runtime.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [docker_arch](#docker_arch)
  - [docker_daemon_command](#docker_daemon_command)
  - [docker_daemon_config](#docker_daemon_config)
  - [docker_daemon_override](#docker_daemon_override)
  - [docker_keyring](#docker_keyring)
  - [docker_mount_flags](#docker_mount_flags)
  - [docker_networks_extra](#docker_networks_extra)
  - [docker_networks_general](#docker_networks_general)
  - [docker_registries_extra](#docker_registries_extra)
  - [docker_registries_general](#docker_registries_general)
  - [docker_upstream_version](#docker_upstream_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### docker_arch

Target system architecture used to select correct deb repository

#### Default value

```YAML
docker_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' or ansible_architecture
  == 'arm64' else 'amd64' }}"
```

### docker_daemon_command

Command executed to start the daemon

#### Default value

```YAML
docker_daemon_command: /usr/bin/dockerd -H unix://
```

### docker_daemon_config

Add config options to daemon.json

#### Default value

```YAML
docker_daemon_config:
  log-driver: json-file
  log-opts:
    max-size: 5m
    max-file: '3'
  live-restore: true
```

### docker_daemon_override

#### Default value

```YAML
docker_daemon_override: false
```

### docker_keyring

Path for the repository keyring

#### Default value

```YAML
docker_keyring: /usr/share/keyrings/docker-archive-keyring.gpg
```

### docker_mount_flags

Optionally define mount flags for systemd

#### Default value

```YAML
docker_mount_flags:
```

### docker_networks_extra

List of extra docker networks to create

#### Default value

```YAML
docker_networks_extra: []
```

#### Example usage

```YAML
docker_networks_extra:
  - name: traefik
    driver: bridge
    enable_ipv6: true
    ipam_config:
      - subnet: fdd1:ac8c:0557:7ce1::/64
    force: false
    state: present
```

### docker_networks_general

List of general docker networks to create

#### Default value

```YAML
docker_networks_general: []
```

#### Example usage

```YAML
docker_networks_general:
  - name: traefik
    driver: bridge
    enable_ipv6: true
    ipam_config:
      - subnet: fdd1:ac8c:0557:7ce1::/64
    force: false
    state: present
```

### docker_registries_extra

List of extra docker registries to auto login

#### Default value

```YAML
docker_registries_extra: []
```

#### Example usage

```YAML
docker_registries_extra:
  - url: myregistry.example.com
    username: docker
    password: secure
    email: docker@example.com
    reauthorize: false
    state: present
```

### docker_registries_general

List of general docker registries to auto login

#### Default value

```YAML
docker_registries_general: '{{ docker_registries | default([]) }}'
```

#### Example usage

```YAML
docker_registries_general:
  - url: myregistry.example.com
    username: docker
    password: secure
    email: docker@example.com
    reauthorize: false
    state: present
```

### docker_upstream_version

Install from upstream repository

#### Default value

```YAML
docker_upstream_version: true
```

## Discovered Tags

**_docker_**

## Dependencies

- [community.docker](https://github.com/ansible-collections/community.docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
