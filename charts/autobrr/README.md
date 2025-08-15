# autobrr

![Version: 0.6.1](https://img.shields.io/badge/Version-0.6.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v1.65.0](https://img.shields.io/badge/AppVersion-v1.65.0-informational?style=flat-square)

An Autobrr Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.2.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.autobrr.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.autobrr.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.autobrr.image.repository | string | `"ghcr.io/autobrr/autobrr"` | image repository |
| controllers.main.containers.autobrr.image.tag | string | `"v1.65.0"` | image tag |
| controllers.main.containers.autobrr.probes.liveness | object | `{"path":"/api/healthz/liveness","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.autobrr.probes.readiness | object | `{"path":"/api/healthz/readiness","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"Recreate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.globalMounts[0].path | string | `"/config"` |  |
| persistence.config.retain | bool | `true` |  |
| persistence.config.size | string | `"500Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

