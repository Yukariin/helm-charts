# vaultwarden

![Version: 0.1.5](https://img.shields.io/badge/Version-0.1.5-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.34.1](https://img.shields.io/badge/AppVersion-1.34.1-informational?style=flat-square)

A Vaultwarden Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.1.2 |
| https://charts.bitnami.com/bitnami | mariadb | 21.0.3 |
| https://charts.bitnami.com/bitnami | postgresql | 16.7.18 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.main.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.main.image.repository | string | `"ghcr.io/dani-garcia/vaultwarden"` | image repository |
| controllers.main.containers.main.image.tag | string | `"1.34.1"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/alive","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/alive","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| mariadb | object | See [values.yaml](./values.yaml) | Enable and configure mariadb database subchart under this key. |
| persistence | object | See [values.yaml](./values.yaml) | Configure persistence settings for the chart under this key. |
| postgresql | object | See [values.yaml](./values.yaml) | Enable and configure postgresql database subchart under this key. |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

