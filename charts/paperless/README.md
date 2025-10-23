# paperless

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.19.1](https://img.shields.io/badge/AppVersion-2.19.1-informational?style=flat-square)

A Paperless Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.3.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env.COMPOSE_PROJECT_NAME | string | `"paperless"` | Project name |
| controllers.main.containers.main.env.PAPERLESS_PORT | int | `8000` |  |
| controllers.main.containers.main.env.PAPERLESS_REDIS | string | `"redis://paperless-redis"` | Redis to use |
| controllers.main.containers.main.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.main.image.repository | string | `"ghcr.io/paperless-ngx/paperless-ngx"` | image repository |
| controllers.main.containers.main.image.tag | string | `"2.19.1"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/","type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.main.resources.limits.memory | string | `"4Gi"` |  |
| controllers.main.containers.main.resources.requests.cpu | string | `"25m"` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"1Gi"` |  |
| controllers.main.strategy | string | `"Recreate"` | Set the controller upgrade strategy |
| controllers.redis.containers.main.image.repository | string | `"ghcr.io/valkey-io/valkey"` |  |
| controllers.redis.containers.main.image.tag | string | `"9.0.0"` |  |
| controllers.redis.containers.main.resources.limits.memory | string | `"128Mi"` |  |
| controllers.redis.containers.main.resources.requests.cpu | string | `"5m"` |  |
| controllers.redis.containers.main.resources.requests.memory | string | `"32Mi"` |  |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.consume.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.consume.advancedMounts.main.main[0].path | string | `"/usr/src/paperless/consume"` |  |
| persistence.consume.enabled | bool | `false` |  |
| persistence.consume.size | string | `"2Gi"` |  |
| persistence.data | object | `{"accessMode":"ReadWriteOnce","advancedMounts":{"main":{"main":[{"path":"/usr/src/paperless/data"}]}},"enabled":true,"size":"1Gi"}` | Paperless data directory (search index, classification model, etc.) |
| persistence.export.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.export.advancedMounts.main.main[0].path | string | `"/usr/src/paperless/export"` |  |
| persistence.export.enabled | bool | `false` |  |
| persistence.export.size | string | `"2Gi"` |  |
| persistence.media | object | `{"accessMode":"ReadWriteOnce","advancedMounts":{"main":{"main":[{"path":"/usr/src/paperless/media"}]}},"enabled":true,"size":"10Gi"}` | Paperless media directory (documents and thumbnails) |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

