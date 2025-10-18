# ollama

![Version: 3.0.8](https://img.shields.io/badge/Version-3.0.8-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.12.6](https://img.shields.io/badge/AppVersion-0.12.6-informational?style=flat-square)

An ollama Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.3.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.env | object | See [values.yaml](./values.yaml) | environment variables. |
| controllers.main.containers.main.image.repository | string | `"docker.io/ollama/ollama"` | image repository |
| controllers.main.containers.main.image.tag | string | `"0.12.6"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/health","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/health","type":"HTTP"}` | Configures readiness probe |
| controllers.ui.containers.main.env.OLLAMA_BASE_URL | string | `"http://ollama-main:11434"` |  |
| controllers.ui.containers.main.image.pullPolicy | string | `"Always"` |  |
| controllers.ui.containers.main.image.repository | string | `"ghcr.io/open-webui/open-webui"` |  |
| controllers.ui.containers.main.image.tag | string | `"main"` |  |
| controllers.ui.containers.main.probes.liveness.path | string | `"/health"` |  |
| controllers.ui.containers.main.probes.liveness.type | string | `"HTTP"` |  |
| controllers.ui.containers.main.probes.readiness.path | string | `"/health"` |  |
| controllers.ui.containers.main.probes.readiness.type | string | `"HTTP"` |  |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| ingress.ui.enabled | bool | `false` |  |
| persistence.data.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.data.advancedMounts.main.main[0].path | string | `"/root/.ollama"` |  |
| persistence.data.advancedMounts.ui.main[0].path | string | `"/app/backend/data"` |  |
| persistence.data.retain | bool | `true` |  |
| persistence.data.size | string | `"10Gi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

