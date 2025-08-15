# gotify

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.6.3](https://img.shields.io/badge/AppVersion-2.6.3-informational?style=flat-square)

A Gotify Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.2.0 |
| https://charts.bitnami.com/bitnami | postgresql | 16.7.26 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. [[ref]](https://gotify.net/docs/config#environment-variables) |
| controllers.main.containers.main.env.GOTIFY_DEFAULTUSER_NAME | string | `"admin"` | Default admin username |
| controllers.main.containers.main.env.GOTIFY_DEFAULTUSER_PASS | string | `"admin"` | Default admin password |
| controllers.main.containers.main.env.GOTIFY_REGISTRATION | string | `"false"` | Allow registration |
| controllers.main.containers.main.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.main.image.repository | string | `"ghcr.io/gotify/server"` | image repository |
| controllers.main.containers.main.image.tag | string | `"2.6.3"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/health","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/health","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See [values.yaml](./values.yaml) | Configure persistence settings for the chart under this key. |
| postgresql | object | See [values.yaml](./values.yaml) | Enable and configure postgresql database subchart under this key.    [[ref]](https://github.com/bitnami/charts/tree/main/bitnami/postgresql) |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

