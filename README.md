# docker

[![Build Status](https://cloud.drone.io/api/badges/rolehippie/docker/status.svg)](https://cloud.drone.io/rolehippie/docker)

Ansible role to configure docker

## Table of content

* [Default Variables](#default-variables)
  * [docker_arch](#docker_arch)
  * [docker_daemon_config](#docker_daemon_config)
  * [docker_registries](#docker_registries)
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

### docker_registries

List of docker registries to auto login

#### Default value

```YAML
docker_registries: []
```

#### Example usage

```YAML
docker_registries:
  - registry: myregistry.example.com
    username: docker
    password: secure
    email: docker@example.com
    reauthorize: False
    state: present
```

## Dependencies

None.

## License

Apache-2.0

## Author

Thomas Boerger
