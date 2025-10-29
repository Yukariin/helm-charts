# cloudflared

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2025.4.2](https://img.shields.io/badge/AppVersion-2025.4.2-informational?style=flat-square)

A cloudflared Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.4.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.args[0] | string | `"tunnel"` |  |
| controllers.main.containers.main.args[1] | string | `"--config"` |  |
| controllers.main.containers.main.args[2] | string | `"/etc/cloudflared/config.yaml"` |  |
| controllers.main.containers.main.args[3] | string | `"run"` |  |
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.main.image.repository | string | `"docker.io/cloudflare/cloudflared"` | image repository |
| controllers.main.containers.main.image.tag | string | `"2025.4.2"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/ready","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/ready","type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.main.resources.limits.memory | string | `"256Mi"` |  |
| controllers.main.containers.main.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"128Mi"` |  |
| controllers.main.strategy | string | `"RollingUpdate"` |  |
| persistence.config.enabled | bool | `true` |  |
| persistence.config.globalMounts[0].path | string | `"/etc/cloudflared/config.yaml"` |  |
| persistence.config.globalMounts[0].readOnly | bool | `true` |  |
| persistence.config.globalMounts[0].subPath | string | `"config.yaml"` |  |
| persistence.config.name | string | `"cloudflared-config"` |  |
| persistence.config.type | string | `"configMap"` |  |
| persistence.credentials.enabled | bool | `true` |  |
| persistence.credentials.globalMounts[0].path | string | `"/etc/cloudflared/credentials.json"` |  |
| persistence.credentials.globalMounts[0].readOnly | bool | `true` |  |
| persistence.credentials.globalMounts[0].subPath | string | `"credentials.json"` |  |
| persistence.credentials.name | string | `"cloudflared-credentials"` |  |
| persistence.credentials.type | string | `"secret"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |
| serviceMonitor.main.enabled | bool | `false` | Enables or disables the serviceMonitor. |
| serviceMonitor.main.endpoints[0].interval | string | `"1m"` |  |
| serviceMonitor.main.endpoints[0].path | string | `"/metrics"` |  |
| serviceMonitor.main.endpoints[0].port | string | `"http"` |  |
| serviceMonitor.main.endpoints[0].scheme | string | `"http"` |  |
| serviceMonitor.main.endpoints[0].scrapeTimeout | string | `"10s"` |  |
| serviceMonitor.main.serviceName | string | See [values.yaml](./values.yaml) | Configures the endpoints for the serviceMonitor. |

