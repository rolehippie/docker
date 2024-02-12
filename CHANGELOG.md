# Changelog

## [2.0.0](https://github.com/rolehippie/docker/compare/v1.2.1...v2.0.0) (2024-02-12)


### Features

* drop support for ubuntu 18.04 ([4c3b544](https://github.com/rolehippie/docker/commit/4c3b5441fe0447bc3384f7d8384fa1da6a228e09))
* used full qualified collection names ([e52293e](https://github.com/rolehippie/docker/commit/e52293ee4bcb199030de9adbb4dfbc64959b0265))


### Bugfixes

* remove meta requirements and document used collections ([6dd8520](https://github.com/rolehippie/docker/commit/6dd8520ff4c98fb5353d03a99fede5548f9cc60d))

## [1.2.1](https://github.com/rolehippie/docker/compare/v1.2.0...v1.2.1) (2023-07-24)


### Bugfixes

* remove old repo with outdated key path ([3d35d2c](https://github.com/rolehippie/docker/commit/3d35d2ca164da20ed02f16bdd12939f9b5a5e419))

## [1.2.0](https://github.com/rolehippie/docker/compare/v1.1.0...v1.2.0) (2023-04-17)


### Features

* drop legacy steps, use unified path for repo key ([9c399d6](https://github.com/rolehippie/docker/commit/9c399d6bbb3055f9f25692110865dc23f3a4c824))

## [1.1.0](https://github.com/rolehippie/docker/compare/v1.0.0...v1.1.0) (2023-01-30)


### Features

* replace old apt key handling ([2af12ee](https://github.com/rolehippie/docker/commit/2af12ee33c3a8d12521c5c779b6a1c6e87265018))


### Bugfixes

* add missing dearmor to new gpg key ([ec39037](https://github.com/rolehippie/docker/commit/ec390376c2cbdfb33ec2501e6399ef0a80d16f80))
* download the right gpg key for repo ([8cbaa0d](https://github.com/rolehippie/docker/commit/8cbaa0d06f48bd8f2fafea292321d2b6456cd515))

## 1.0.0 (2023-01-03)

### Features

* integrated automated release process ([47e3622](https://github.com/rolehippie/docker/commit/47e3622846756f40ad08431b572f98a361ab1728))


### Bugfixes

* resolve no module named distutils.spawn issues ([e4b6133](https://github.com/rolehippie/docker/commit/e4b613391e9df99c0888d9e205c556189676f8a3))
* stop removing credential helper, it kills the idempotence ([89d77de](https://github.com/rolehippie/docker/commit/89d77de1b8fea017386fc2ed5563c27881e4f181))
