# vaultwarden

![Version: 0.1.18](https://img.shields.io/badge/Version-0.1.18-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.34.3](https://img.shields.io/badge/AppVersion-1.34.3-informational?style=flat-square)

A Vaultwarden Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.3.0 |
| https://charts.bitnami.com/bitnami | mariadb | 23.0.4 |
| https://charts.bitnami.com/bitnami | postgresql | 16.7.27 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. [[ref]](https://github.com/dani-garcia/vaultwarden/blob/main/.env.template) |
| controllers.main.containers.main.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.main.image.repository | string | `"ghcr.io/dani-garcia/vaultwarden"` | image repository |
| controllers.main.containers.main.image.tag | string | `"1.34.3"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/alive","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/alive","type":"HTTP"}` | Configures readiness probe |
| controllers.main.containers.main.resources.limits.memory | string | `"256Mi"` |  |
| controllers.main.containers.main.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.main.resources.requests.memory | string | `"64Mi"` |  |
| controllers.main.strategy | string | `"Recreate"` | Set the controller upgrade strategy |
| ingress | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| mariadb | object | See [values.yaml](./values.yaml) | Enable and configure mariadb database subchart under this key. |
| persistence | object | See [values.yaml](./values.yaml) | Configure persistence settings for the chart under this key. |
| postgresql | object | See [values.yaml](./values.yaml) | Enable and configure postgresql database subchart under this key. |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

