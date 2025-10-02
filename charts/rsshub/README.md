# rsshub

![Version: 2.0.1](https://img.shields.io/badge/Version-2.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: latest](https://img.shields.io/badge/AppVersion-latest-informational?style=flat-square)

An RSShub Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.3.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.browserless.image.repository | string | `"ghcr.io/browserless/chrome"` |  |
| controllers.main.containers.browserless.image.tag | string | `"v2.37.0"` |  |
| controllers.main.containers.browserless.ports[0].containerPort | int | `3000` |  |
| controllers.main.containers.browserless.probes.liveness.path | string | `"/pressure"` |  |
| controllers.main.containers.browserless.probes.liveness.type | string | `"HTTP"` |  |
| controllers.main.containers.browserless.probes.readiness.path | string | `"/pressure"` |  |
| controllers.main.containers.browserless.probes.readiness.type | string | `"HTTP"` |  |
| controllers.main.containers.browserless.resources.limits.memory | string | `"2Gi"` |  |
| controllers.main.containers.browserless.resources.requests.cpu | string | `"10m"` |  |
| controllers.main.containers.browserless.resources.requests.memory | string | `"128Mi"` |  |
| controllers.main.containers.redis.image.repository | string | `"ghcr.io/valkey-io/valkey"` |  |
| controllers.main.containers.redis.image.tag | string | `"8.1.3"` |  |
| controllers.main.containers.redis.ports[0].containerPort | int | `6379` |  |
| controllers.main.containers.redis.resources.limits.memory | string | `"256Mi"` |  |
| controllers.main.containers.redis.resources.requests.cpu | string | `"5m"` |  |
| controllers.main.containers.redis.resources.requests.memory | string | `"64Mi"` |  |
| controllers.main.containers.rsshub.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.rsshub.image.pullPolicy | string | `"Always"` | image pull policy |
| controllers.main.containers.rsshub.image.repository | string | `"diygod/rsshub"` | image repository |
| controllers.main.containers.rsshub.image.tag | string | `"latest"` | image tag |
| controllers.main.containers.rsshub.probes.liveness | object | `{"path":"/healthz","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.rsshub.probes.readiness | object | `{"path":"/healthz","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

