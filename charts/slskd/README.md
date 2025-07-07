# slskd

![Version: 0.3.1](https://img.shields.io/badge/Version-0.3.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.23.1](https://img.shields.io/badge/AppVersion-0.23.1-informational?style=flat-square)

An slskd Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://yukariin.github.io/helm-charts | common | 0.1.1 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| deployments.main.autoscaling.enabled | bool | `false` |  |
| deployments.main.autoscaling.maxReplicas | int | `100` |  |
| deployments.main.autoscaling.minReplicas | int | `1` |  |
| deployments.main.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| deployments.main.image.pullPolicy | string | `"IfNotPresent"` |  |
| deployments.main.image.repository | string | `"ghcr.io/slskd/slskd"` |  |
| deployments.main.image.tag | string | `""` |  |
| deployments.main.livenessProbe.httpGet.path | string | `"/health"` |  |
| deployments.main.livenessProbe.httpGet.port | string | `"http"` |  |
| deployments.main.ports[0].containerPort | int | `5030` |  |
| deployments.main.ports[0].name | string | `"http"` |  |
| deployments.main.ports[0].protocol | string | `"TCP"` |  |
| deployments.main.ports[1].containerPort | int | `50300` |  |
| deployments.main.ports[1].name | string | `"slsk"` |  |
| deployments.main.ports[1].protocol | string | `"TCP"` |  |
| deployments.main.readinessProbe.httpGet.path | string | `"/health"` |  |
| deployments.main.readinessProbe.httpGet.port | string | `"http"` |  |
| deployments.main.replicaCount | int | `1` |  |
| deployments.main.resources | object | `{}` |  |
| fullnameOverride | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.main.annotations | object | `{}` |  |
| ingress.main.className | string | `""` |  |
| ingress.main.enabled | bool | `false` |  |
| ingress.main.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.main.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.main.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.main.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| persistence.app.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.app.enabled | bool | `true` |  |
| persistence.app.mountPath | string | `"/app"` |  |
| persistence.app.size | string | `"500Mi"` |  |
| persistence.app.storageClass | string | `""` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| securityContext | object | `{}` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.automount | bool | `true` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| services.main.ports[0].name | string | `"http"` |  |
| services.main.ports[0].port | int | `5030` |  |
| services.main.ports[0].protocol | string | `"TCP"` |  |
| services.main.ports[0].targetPort | string | `"http"` |  |
| services.main.ports[1].name | string | `"slsk"` |  |
| services.main.ports[1].port | int | `50300` |  |
| services.main.ports[1].protocol | string | `"TCP"` |  |
| services.main.ports[1].targetPort | string | `"slsk"` |  |
| services.main.type | string | `"ClusterIP"` |  |
| tolerations | list | `[]` |  |
| volumes | list | `[]` |  |

