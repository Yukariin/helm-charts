# jellyseerr

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.7.3](https://img.shields.io/badge/AppVersion-2.7.3-informational?style=flat-square)

A Jellyseerr Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.4.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.main.image.repository | string | `"docker.io/fallenbagel/jellyseerr"` | image repository |
| controllers.main.containers.main.image.tag | string | `"2.7.3"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/api/v1/status","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/api/v1/status","type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.main.resources.limits.memory | string | `"2Gi"` |  |
| controllers.main.containers.main.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"256Mi"` |  |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.globalMounts[0].path | string | `"/app/config"` |  |
| persistence.config.retain | bool | `true` |  |
| persistence.config.size | string | `"500Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

