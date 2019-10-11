# docker

[![Build Status](https://cloud.drone.io/api/badges/rolehippie/docker/status.svg)](https://cloud.drone.io/rolehippie/docker)

Ansible role to configure docker

## Table of content

* [Default Variables](#default-variables)
  * [docker_opts](#docker_opts)
  * [docker_registries](#docker_registries)
  * [docker_arch](#docker_arch)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---
## Default Variables

### docker_opts

#### Default value

```YAML
docker_opts:
```

### docker_registries

Automatic login to all given registries.

#### Default value

```YAML
docker_registries: []
```

#### Example usage

```YAML
docker_registries:
  - registry: "myregistry.example.com"
    username: "docker"
    password: "secure"
    email: "docker@example.com"
    reauthorize: "no"
    state: "present"
```


### docker_arch

#### Default value

```YAML
docker_arch: amd64
```

## Dependencies

None.

## License

Apache-2.0

## Author

Thomas Boerger

