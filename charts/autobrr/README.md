# autobrr

![Version: 0.2.1](https://img.shields.io/badge/Version-0.2.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v1.63.1](https://img.shields.io/badge/AppVersion-v1.63.1-informational?style=flat-square)

An Autobrr Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 1.5.1 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controller.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/autobrr/autobrr"` | image repository |
| image.tag | string | `nil` | image tag |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config.enabled | bool | `true` |  |
| persistence.config.mountPath | string | `"/config"` |  |
| persistence.config.size | string | `"500Mi"` |  |
| probes.liveness | object | `{"path":"/api/healthz/liveness","type":"HTTP"}` | Configures liveness probe |
| probes.readiness | object | `{"path":"/api/healthz/readiness","type":"HTTP"}` | Configures readiness probe |
| redis | object | See [values.yaml](./values.yaml) | Enable and configure redis subchart under this key.    For more options see [redis chart documentation](https://github.com/bitnami/charts/tree/main/bitnami/redis) |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

