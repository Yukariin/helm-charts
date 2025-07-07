# prowlarr

![Version: 0.2.0](https://img.shields.io/badge/Version-0.2.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.37.0.5076-ls120](https://img.shields.io/badge/AppVersion-1.37.0.5076--ls120-informational?style=flat-square)

A Prowlarr Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| file://../common | common | 0.1.1 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| deployments.main.autoscaling.enabled | bool | `false` |  |
| deployments.main.autoscaling.maxReplicas | int | `100` |  |
| deployments.main.autoscaling.minReplicas | int | `1` |  |
| deployments.main.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| deployments.main.image.pullPolicy | string | `"IfNotPresent"` |  |
| deployments.main.image.repository | string | `"ghcr.io/linuxserver/prowlarr"` |  |
| deployments.main.image.tag | string | `""` |  |
| deployments.main.livenessProbe.httpGet.path | string | `"/ping"` |  |
| deployments.main.livenessProbe.httpGet.port | string | `"http"` |  |
| deployments.main.ports[0].containerPort | int | `9696` |  |
| deployments.main.ports[0].name | string | `"http"` |  |
| deployments.main.ports[0].protocol | string | `"TCP"` |  |
| deployments.main.readinessProbe.httpGet.path | string | `"/ping"` |  |
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
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.enabled | bool | `true` |  |
| persistence.config.mountPath | string | `"/config"` |  |
| persistence.config.size | string | `"500Mi"` |  |
| persistence.config.storageClass | string | `""` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| securityContext | object | `{}` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.automount | bool | `true` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| services.main.ports[0].name | string | `"http"` |  |
| services.main.ports[0].port | int | `9696` |  |
| services.main.ports[0].protocol | string | `"TCP"` |  |
| services.main.ports[0].targetPort | string | `"http"` |  |
| services.main.type | string | `"ClusterIP"` |  |
| tolerations | list | `[]` |  |
| volumes | list | `[]` |  |

