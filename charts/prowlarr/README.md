# prowlarr

![Version: 0.4.1](https://img.shields.io/badge/Version-0.4.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.37.0.5076-ls120](https://img.shields.io/badge/AppVersion-1.37.0.5076--ls120-informational?style=flat-square)

A Prowlarr Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.2.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.prowlarr.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.prowlarr.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.prowlarr.image.repository | string | `"ghcr.io/linuxserver/prowlarr"` | image repository |
| controllers.main.containers.prowlarr.image.tag | string | `"1.37.0.5076-ls120"` | image tag |
| controllers.main.containers.prowlarr.probes.liveness | object | `{"path":"/ping","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.prowlarr.probes.readiness | object | `{"path":"/ping","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.globalMounts[0].path | string | `"/config"` |  |
| persistence.config.retain | bool | `true` |  |
| persistence.config.size | string | `"500Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

