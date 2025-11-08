# paperless

![Version: 2.2.0](https://img.shields.io/badge/Version-2.2.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.19.5](https://img.shields.io/badge/AppVersion-2.19.5-informational?style=flat-square)

A Paperless Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://apache.jfrog.io/artifactory/tika | tika | 2.9.0 |
| https://bjw-s-labs.github.io/helm-charts | common | 4.4.0 |
| https://maikumori.github.io/helm-charts | gotenberg | 1.9.1 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.paperless.containers.main.env.COMPOSE_PROJECT_NAME | string | `"paperless"` | Project name |
| controllers.paperless.containers.main.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.paperless.containers.main.image.repository | string | `"ghcr.io/paperless-ngx/paperless-ngx"` | image repository |
| controllers.paperless.containers.main.image.tag | string | `"2.19.5"` | image tag |
| controllers.paperless.containers.main.probes.liveness | object | `{"path":"/","type":"HTTP"}` | Configures liveness probe |
| controllers.paperless.containers.main.probes.readiness | object | `{"path":"/","type":"HTTP"}` | Configures readiness probe |
| controllers.paperless.containers.main.resources.limits.memory | string | `"4Gi"` |  |
| controllers.paperless.containers.main.resources.requests.cpu | string | `"25m"` |  |
| controllers.paperless.containers.main.resources.requests.memory | string | `"1Gi"` |  |
| controllers.paperless.strategy | string | `"Recreate"` | Set the controller upgrade strategy |
| controllers.redis.containers.main.image.repository | string | `"ghcr.io/valkey-io/valkey"` |  |
| controllers.redis.containers.main.image.tag | string | `"9.0.0"` |  |
| controllers.redis.containers.main.resources.limits.memory | string | `"128Mi"` |  |
| controllers.redis.containers.main.resources.requests.cpu | string | `"5m"` |  |
| controllers.redis.containers.main.resources.requests.memory | string | `"32Mi"` |  |
| controllers.redis.strategy | string | `"Recreate"` |  |
| gotenberg.chromium.allowList | string | `"file:///tmp/.*"` |  |
| gotenberg.chromium.disableJavaScript | bool | `true` |  |
| gotenberg.chromium.maxQueueSize | int | `2` |  |
| gotenberg.enabled | bool | `false` |  |
| gotenberg.ingress.enabled | bool | `false` |  |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.consume.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.consume.advancedMounts.main.main[0].path | string | `"/usr/src/paperless/consume"` |  |
| persistence.consume.enabled | bool | `false` |  |
| persistence.consume.size | string | `"2Gi"` |  |
| persistence.data | object | `{"accessMode":"ReadWriteOnce","advancedMounts":{"main":{"main":[{"path":"/usr/src/paperless/data"}]}},"enabled":true,"size":"500Mi"}` | Paperless data directory (search index, classification model, etc.) |
| persistence.export.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.export.advancedMounts.main.main[0].path | string | `"/usr/src/paperless/export"` |  |
| persistence.export.enabled | bool | `false` |  |
| persistence.export.size | string | `"2Gi"` |  |
| persistence.media | object | `{"accessMode":"ReadWriteOnce","advancedMounts":{"main":{"main":[{"path":"/usr/src/paperless/media"}]}},"enabled":false,"size":"10Gi"}` | Paperless media directory (documents and thumbnails) |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |
| tika.enabled | bool | `false` |  |
| tika.ingress.enabled | bool | `false` |  |

