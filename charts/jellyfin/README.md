# jellyfin

![Version: 2.3.0](https://img.shields.io/badge/Version-2.3.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 10.11.0](https://img.shields.io/badge/AppVersion-10.11.0-informational?style=flat-square)

A Jellyfin Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.4.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.main.image.repository | string | `"ghcr.io/linuxserver/jellyfin"` | image repository |
| controllers.main.containers.main.image.tag | string | `"10.11.0"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/health","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/health","type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.main.resources.limits.memory | string | `"2Gi"` |  |
| controllers.main.containers.main.resources.requests.cpu | int | `1` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"512Mi"` |  |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.cache.enabled | bool | `true` |  |
| persistence.cache.globalMounts[0].path | string | `"/config/cache"` |  |
| persistence.cache.type | string | `"emptyDir"` |  |
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.enabled | bool | `true` |  |
| persistence.config.globalMounts[0].path | string | `"/config"` |  |
| persistence.config.size | string | `"2Gi"` |  |
| persistence.transcode.enabled | bool | `true` |  |
| persistence.transcode.globalMounts[0].path | string | `"/config/transcodes"` |  |
| persistence.transcode.type | string | `"emptyDir"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |
| serviceMonitor.main.enabled | bool | `false` | Enables or disables the serviceMonitor. |
| serviceMonitor.main.endpoints[0].interval | string | `"1m"` |  |
| serviceMonitor.main.endpoints[0].path | string | `"/metrics"` |  |
| serviceMonitor.main.endpoints[0].port | string | `"http"` |  |
| serviceMonitor.main.endpoints[0].scheme | string | `"http"` |  |
| serviceMonitor.main.endpoints[0].scrapeTimeout | string | `"10s"` |  |
| serviceMonitor.main.serviceName | string | See [values.yaml](./values.yaml) | Configures the endpoints for the serviceMonitor. |

