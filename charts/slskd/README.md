# slskd

![Version: 2.0.1](https://img.shields.io/badge/Version-2.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.24.0](https://img.shields.io/badge/AppVersion-0.24.0-informational?style=flat-square)

An slskd Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.4.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.gluetun.env | object | See [values.yaml](./values.yaml) | environment variables. [[ref]](https://github.com/qdm12/gluetun-wiki) |
| controllers.main.containers.gluetun.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.gluetun.image.repository | string | `"qmcgaw/gluetun"` | image repository |
| controllers.main.containers.gluetun.image.tag | string | `"v3.40.3"` | image tag |
| controllers.main.containers.gluetun.securityContext.capabilities.add[0] | string | `"NET_ADMIN"` |  |
| controllers.main.containers.slskd.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.slskd.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.slskd.image.repository | string | `"ghcr.io/slskd/slskd"` | image repository |
| controllers.main.containers.slskd.image.tag | string | `"0.24.0"` | image tag |
| controllers.main.containers.slskd.probes.liveness | object | `{"path":"/health","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.slskd.probes.readiness | object | `{"path":"/health","type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.slskd.resources.limits.memory | string | `"1Gi"` |  |
| controllers.main.containers.slskd.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.slskd.resources.requests.memory | string | `"128Mi"` |  |
| controllers.main.strategy | string | `"Recreate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.app.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.app.advancedMounts.main.slskd[0].path | string | `"/app"` |  |
| persistence.app.enabled | bool | `true` |  |
| persistence.app.size | string | `"500Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |
| serviceMonitor | object | See [values.yaml](./values.yaml) | Configure the ServiceMonitors for the chart here. |
| serviceMonitor.main.enabled | bool | `false` | Enables or disables the serviceMonitor. |
| serviceMonitor.main.endpoints | list | See [values.yaml](./values.yaml) | Configures the endpoints for the serviceMonitor. Helm templates can be used. |
| soulseek.password | string | `""` | Soulseek password |
| soulseek.user | string | `""` | Soulseek username |
| webui.auth.disabled | bool | `false` | Disable WebUI authentication |
| webui.auth.jwt_key | string | `""` | JWT secret key for authentication (optional) |
| webui.auth.password | string | `"admin123"` | WebUI password |
| webui.auth.user | string | `"admin"` | WebUI username |

