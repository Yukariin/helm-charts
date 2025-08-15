# sillytavern

![Version: 0.3.0](https://img.shields.io/badge/Version-0.3.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: staging](https://img.shields.io/badge/AppVersion-staging-informational?style=flat-square)

A SillyTavern Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.2.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.main.image.pullPolicy | string | `"Always"` | image pull policy |
| controllers.main.containers.main.image.repository | string | `"ghcr.io/sillytavern/sillytavern"` | image repository |
| controllers.main.containers.main.image.tag | string | `"staging"` | image tag |
| controllers.main.containers.main.resources.limits.cpu | string | `"1"` |  |
| controllers.main.containers.main.resources.limits.memory | string | `"1Gi"` |  |
| controllers.main.containers.main.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"128Mi"` |  |
| controllers.main.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config.globalMounts[0].path | string | `"/home/node/app/config/config.yaml"` |  |
| persistence.config.globalMounts[0].subPath | string | `"config.yaml"` |  |
| persistence.config.name | string | `"sillytavern-config"` |  |
| persistence.config.type | string | `"configMap"` |  |
| persistence.main.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.main.enabled | bool | `true` |  |
| persistence.main.globalMounts[0].path | string | `"/home/node/app/data"` |  |
| persistence.main.globalMounts[0].subPath | string | `"data"` |  |
| persistence.main.globalMounts[1].path | string | `"/home/node/app/plugins"` |  |
| persistence.main.globalMounts[1].subPath | string | `"plugins"` |  |
| persistence.main.globalMounts[2].path | string | `"/home/node/app/public/scripts/extensions/third-party"` |  |
| persistence.main.globalMounts[2].subPath | string | `"extensions"` |  |
| persistence.main.retain | bool | `true` |  |
| persistence.main.size | string | `"1Gi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

