# calibre-web-automated

![Version: 1.1.0](https://img.shields.io/badge/Version-1.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: V3.1.4](https://img.shields.io/badge/AppVersion-V3.1.4-informational?style=flat-square)

A Calibre-Web-Automated Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.4.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.main.image.repository | string | `"ghcr.io/crocodilestick/calibre-web-automated"` | image repository |
| controllers.main.containers.main.image.tag | string | `"V3.1.4"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/health","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/health","type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.main.resources.limits.memory | string | `"1Gi"` |  |
| controllers.main.containers.main.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"128Mi"` |  |
| controllers.main.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.globalMounts[0].path | string | `"/config"` |  |
| persistence.config.retain | bool | `true` |  |
| persistence.config.size | string | `"500Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

