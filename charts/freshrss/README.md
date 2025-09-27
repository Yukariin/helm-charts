# freshrss

![Version: 0.4.0](https://img.shields.io/badge/Version-0.4.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.27.0](https://img.shields.io/badge/AppVersion-1.27.0-informational?style=flat-square)

A FreshRSS Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.3.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env.CRON_MIN | string | `"*/20"` |  |
| controllers.main.containers.main.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.main.image.repository | string | `"freshrss/freshrss"` | image repository |
| controllers.main.containers.main.image.tag | string | `"1.27.0"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/i/","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/i/","type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.main.resources.limits.memory | string | `"256Mi"` |  |
| controllers.main.containers.main.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"64Mi"` |  |
| controllers.main.strategy | string | `"Recreate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.data.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.data.globalMounts[0].path | string | `"/var/www/FreshRSS/data"` |  |
| persistence.data.retain | bool | `true` |  |
| persistence.data.size | string | `"500Mi"` |  |
| persistence.extensions.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.extensions.globalMounts[0].path | string | `"/var/www/FreshRSS/extensions"` |  |
| persistence.extensions.size | string | `"500Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

