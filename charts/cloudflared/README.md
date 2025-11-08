# cloudflared

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2025.10.1](https://img.shields.io/badge/AppVersion-2025.10.1-informational?style=flat-square)

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
| controllers.main.containers.main.image.tag | string | `"2025.10.1"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/ready","port":8080,"type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/ready","port":8080,"type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.main.resources.limits.cpu | string | `"100m"` |  |
| controllers.main.containers.main.resources.limits.memory | string | `"256Mi"` |  |
| controllers.main.containers.main.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"128Mi"` |  |
| controllers.main.strategy | string | `"RollingUpdate"` |  |
| persistence | object | `{"config":{"enabled":true,"globalMounts":[{"path":"/etc/cloudflared/config.yaml","readOnly":true,"subPath":"config.yaml"}],"name":"{{ .Release.Name }}-config","type":"configMap"},"credentials":{"enabled":true,"globalMounts":[{"path":"/etc/cloudflared/credentials.json","readOnly":true,"subPath":"credentials.json"}],"name":"{{ .Release.Name }}-credentials","type":"secret"}}` | Persistence configuration for config and credentials |
| securityContext | object | `{"container":{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"readOnlyRootFilesystem":true,"runAsGroup":65534,"runAsNonRoot":true,"runAsUser":65534}}` | Configure the security context for the container |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |
| serviceMonitor.main.enabled | bool | `false` | Enables or disables the serviceMonitor. |
| serviceMonitor.main.endpoints[0].interval | string | `"1m"` |  |
| serviceMonitor.main.endpoints[0].path | string | `"/metrics"` |  |
| serviceMonitor.main.endpoints[0].port | string | `"http"` |  |
| serviceMonitor.main.endpoints[0].scheme | string | `"http"` |  |
| serviceMonitor.main.endpoints[0].scrapeTimeout | string | `"10s"` |  |
| serviceMonitor.main.serviceName | string | See [values.yaml](./values.yaml) | Configures the endpoints for the serviceMonitor. |
| tunnelName | string | `"your-tunnel-name"` | Cloudflare tunnel name (used in config.yaml) |

