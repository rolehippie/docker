# docker

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/docker) [![Build Status](https://img.shields.io/drone/build/rolehippie/docker/master?logo=drone)](https://cloud.drone.io/rolehippie/docker) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/docker)](https://github.com/rolehippie/docker/blob/master/LICENSE) 

Ansible role to install and configure Docker container runtime. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [docker_arch](#docker_arch)
  * [docker_daemon_command](#docker_daemon_command)
  * [docker_daemon_config](#docker_daemon_config)
  * [docker_daemon_override](#docker_daemon_override)
  * [docker_mount_flags](#docker_mount_flags)
  * [docker_networks_extra](#docker_networks_extra)
  * [docker_networks_general](#docker_networks_general)
  * [docker_registries_extra](#docker_registries_extra)
  * [docker_registries_general](#docker_registries_general)
  * [docker_upstream_version](#docker_upstream_version)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### docker_arch

Target system architecture used to select correct deb repository

#### Default value

```YAML
docker_arch: amd64
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
    enable_ipv6: True
    ipam_config:
      - subnet: fdd1:ac8c:0557:7ce1::/64
    force: False
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
    enable_ipv6: True
    ipam_config:
      - subnet: fdd1:ac8c:0557:7ce1::/64
    force: False
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
    reauthorize: False
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
    reauthorize: False
    state: present
```

### docker_upstream_version

Install from upstream repository

#### Default value

```YAML
docker_upstream_version: true
```

## Dependencies

* None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
