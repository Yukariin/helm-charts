# slskd

![Version: 0.8.2](https://img.shields.io/badge/Version-0.8.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.23.1](https://img.shields.io/badge/AppVersion-0.23.1-informational?style=flat-square)

An slskd Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.1.2 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.gluetun.env | object | See [values.yaml](./values.yaml) | environment variables. [[ref]](https://github.com/qdm12/gluetun-wiki) |
| controllers.main.containers.gluetun.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.gluetun.image.repository | string | `"qmcgaw/gluetun"` | image repository |
| controllers.main.containers.gluetun.image.tag | string | `"v3.40.0"` | image tag |
| controllers.main.containers.gluetun.securityContext.capabilities.add[0] | string | `"NET_ADMIN"` |  |
| controllers.main.containers.slskd.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.slskd.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.slskd.image.repository | string | `"ghcr.io/slskd/slskd"` | image repository |
| controllers.main.containers.slskd.image.tag | string | `"0.23.1"` | image tag |
| controllers.main.containers.slskd.probes.liveness | object | `{"path":"/health","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.slskd.probes.readiness | object | `{"path":"/health","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"Recreate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.app.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.app.advancedMounts.main.slskd[0].path | string | `"/app"` |  |
| persistence.app.retain | bool | `true` |  |
| persistence.app.size | string | `"500Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |
| serviceMonitor | object | See [values.yaml](./values.yaml) | Configure the ServiceMonitors for the chart here. |
| serviceMonitor.main.enabled | bool | `false` | Enables or disables the serviceMonitor. |
| serviceMonitor.main.endpoints | list | See [values.yaml](./values.yaml) | Configures the endpoints for the serviceMonitor. Helm templates can be used. |

