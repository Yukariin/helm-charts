# rsshub

![Version: 0.2.4](https://img.shields.io/badge/Version-0.2.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2025-07-05](https://img.shields.io/badge/AppVersion-2025--07--05-informational?style=flat-square)

An RSShub Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.1.2 |
| https://charts.bitnami.com/bitnami | redis | 21.2.10 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.browserless.image.repository | string | `"browserless/chrome"` |  |
| controllers.main.containers.browserless.image.tag | string | `"latest"` |  |
| controllers.main.containers.browserless.ports[0].containerPort | int | `3000` |  |
| controllers.main.containers.browserless.probes.liveness.path | string | `"/pressure"` |  |
| controllers.main.containers.browserless.probes.liveness.type | string | `"HTTP"` |  |
| controllers.main.containers.browserless.probes.readiness.path | string | `"/pressure"` |  |
| controllers.main.containers.browserless.probes.readiness.type | string | `"HTTP"` |  |
| controllers.main.containers.rsshub.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.rsshub.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.rsshub.image.repository | string | `"diygod/rsshub"` | image repository |
| controllers.main.containers.rsshub.image.tag | string | `"2025-07-04"` | image tag |
| controllers.main.containers.rsshub.probes.liveness | object | `{"path":"/healthz","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.rsshub.probes.readiness | object | `{"path":"/healthz","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| redis | object | See [values.yaml](./values.yaml) | Enable and configure redis subchart under this key.    For more options see [redis chart documentation](https://github.com/bitnami/charts/tree/main/bitnami/redis) |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

