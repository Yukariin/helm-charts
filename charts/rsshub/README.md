# rsshub

![Version: 3.0.0](https://img.shields.io/badge/Version-3.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: latest](https://img.shields.io/badge/AppVersion-latest-informational?style=flat-square)

An RSShub Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.3.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.browserless.containers.main.image.repository | string | `"ghcr.io/browserless/chrome"` |  |
| controllers.browserless.containers.main.image.tag | string | `"v2.37.0"` |  |
| controllers.browserless.containers.main.probes.liveness.path | string | `"/pressure"` |  |
| controllers.browserless.containers.main.probes.liveness.type | string | `"HTTP"` |  |
| controllers.browserless.containers.main.probes.readiness.path | string | `"/pressure"` |  |
| controllers.browserless.containers.main.probes.readiness.type | string | `"HTTP"` |  |
| controllers.browserless.containers.main.resources.limits.memory | string | `"2Gi"` |  |
| controllers.browserless.containers.main.resources.requests.cpu | string | `"10m"` |  |
| controllers.browserless.containers.main.resources.requests.memory | string | `"128Mi"` |  |
| controllers.redis.containers.main.image.repository | string | `"ghcr.io/valkey-io/valkey"` |  |
| controllers.redis.containers.main.image.tag | string | `"8.1.3"` |  |
| controllers.redis.containers.main.resources.limits.memory | string | `"256Mi"` |  |
| controllers.redis.containers.main.resources.requests.cpu | string | `"5m"` |  |
| controllers.redis.containers.main.resources.requests.memory | string | `"64Mi"` |  |
| controllers.rsshub.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.rsshub.containers.main.image.pullPolicy | string | `"Always"` | image pull policy |
| controllers.rsshub.containers.main.image.repository | string | `"ghcr.io/diygod/rsshub"` | image repository |
| controllers.rsshub.containers.main.image.tag | string | `"latest"` | image tag |
| controllers.rsshub.containers.main.probes.liveness | object | `{"path":"/healthz","type":"HTTP"}` | Configures liveness probe |
| controllers.rsshub.containers.main.probes.readiness | object | `{"path":"/healthz","type":"HTTP"}` | Configures readiness probe |
| controllers.rsshub.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

