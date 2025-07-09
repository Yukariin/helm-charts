# navidrome

![Version: 0.3.1](https://img.shields.io/badge/Version-0.3.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.57.0](https://img.shields.io/badge/AppVersion-0.57.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.1.2 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.navidrome.env | object | See [values.yaml](./values.yaml) | environment variables. [[ref]](https://www.navidrome.org/docs/usage/configuration-options/#environment-variables) |
| controllers.main.containers.navidrome.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.navidrome.image.repository | string | `"deluan/navidrome"` | image repository |
| controllers.main.containers.navidrome.image.tag | string | `"0.57.0"` | image tag |
| controllers.main.containers.navidrome.probes.liveness | object | `{"path":"/ping","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.navidrome.probes.readiness | object | `{"path":"/ping","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.globalMounts[0].path | string | `"/config"` |  |
| persistence.config.retain | bool | `true` |  |
| persistence.config.size | string | `"800Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

