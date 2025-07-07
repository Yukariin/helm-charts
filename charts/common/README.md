# common

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: library](https://img.shields.io/badge/Type-library-informational?style=flat-square) ![AppVersion: 1.0](https://img.shields.io/badge/AppVersion-1.0-informational?style=flat-square)

A library chart for common Kubernetes resources

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| deployments.main.affinity | object | `{}` |  |
| deployments.main.autoscaling.behavior | object | `{}` |  |
| deployments.main.autoscaling.customMetrics | list | `[]` |  |
| deployments.main.autoscaling.enabled | bool | `false` |  |
| deployments.main.autoscaling.maxReplicas | int | `100` |  |
| deployments.main.autoscaling.minReplicas | int | `1` |  |
| deployments.main.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| deployments.main.autoscaling.targetMemoryUtilizationPercentage | int | `80` |  |
| deployments.main.env.ENV_VAR | string | `"value"` |  |
| deployments.main.envFrom | list | `[]` |  |
| deployments.main.image.pullPolicy | string | `"IfNotPresent"` |  |
| deployments.main.image.repository | string | `"nginx"` |  |
| deployments.main.image.tag | string | `"1.21"` |  |
| deployments.main.imagePullSecrets | list | `[]` |  |
| deployments.main.livenessProbe.httpGet.path | string | `"/"` |  |
| deployments.main.livenessProbe.httpGet.port | string | `"http"` |  |
| deployments.main.livenessProbe.initialDelaySeconds | int | `30` |  |
| deployments.main.livenessProbe.periodSeconds | int | `10` |  |
| deployments.main.nodeSelector | object | `{}` |  |
| deployments.main.podSecurityContext | object | `{}` |  |
| deployments.main.ports[0].containerPort | int | `80` |  |
| deployments.main.ports[0].name | string | `"http"` |  |
| deployments.main.ports[0].protocol | string | `"TCP"` |  |
| deployments.main.readinessProbe.httpGet.path | string | `"/"` |  |
| deployments.main.readinessProbe.httpGet.port | string | `"http"` |  |
| deployments.main.readinessProbe.initialDelaySeconds | int | `5` |  |
| deployments.main.readinessProbe.periodSeconds | int | `5` |  |
| deployments.main.replicaCount | int | `1` |  |
| deployments.main.resources.limits.cpu | string | `"500m"` |  |
| deployments.main.resources.limits.memory | string | `"512Mi"` |  |
| deployments.main.resources.requests.cpu | string | `"250m"` |  |
| deployments.main.resources.requests.memory | string | `"256Mi"` |  |
| deployments.main.securityContext | object | `{}` |  |
| deployments.main.sidecars[0].env.BACKUP_SCHEDULE | string | `"0 2 * * *"` |  |
| deployments.main.sidecars[0].image.pullPolicy | string | `"IfNotPresent"` |  |
| deployments.main.sidecars[0].image.repository | string | `"backup-tool"` |  |
| deployments.main.sidecars[0].image.tag | string | `"latest"` |  |
| deployments.main.sidecars[0].name | string | `"backup"` |  |
| deployments.main.sidecars[0].persistenceAccess[0] | string | `"data"` |  |
| deployments.main.sidecars[0].resources.limits.cpu | string | `"100m"` |  |
| deployments.main.sidecars[0].resources.limits.memory | string | `"128Mi"` |  |
| deployments.main.sidecars[0].volumeMounts[0].mountPath | string | `"/etc/backup"` |  |
| deployments.main.sidecars[0].volumeMounts[0].name | string | `"backup-config"` |  |
| deployments.main.startupProbe | object | `{}` |  |
| deployments.main.tolerations | list | `[]` |  |
| deployments.main.volumeMounts | list | `[]` |  |
| deployments.main.volumes | list | `[]` |  |
| deployments.worker.env.WORKER_TYPE | string | `"background"` |  |
| deployments.worker.image.repository | string | `"worker-app"` |  |
| deployments.worker.image.tag | string | `"latest"` |  |
| deployments.worker.replicaCount | int | `2` |  |
| deployments.worker.resources.limits.cpu | string | `"200m"` |  |
| deployments.worker.resources.limits.memory | string | `"256Mi"` |  |
| fullnameOverride | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.main.annotations | object | `{}` |  |
| ingress.main.className | string | `""` |  |
| ingress.main.enabled | bool | `false` |  |
| ingress.main.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.main.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.main.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.main.hosts[0].paths[0].serviceName | string | `""` |  |
| ingress.main.hosts[0].paths[0].servicePort | int | `80` |  |
| ingress.main.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.enabled | bool | `false` |  |
| persistence.config.mountPath | string | `"/config"` |  |
| persistence.config.size | string | `"100Mi"` |  |
| persistence.config.storageClass | string | `""` |  |
| persistence.data.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.data.accessModes | list | `[]` |  |
| persistence.data.annotations | object | `{}` |  |
| persistence.data.dataSource | object | `{}` |  |
| persistence.data.dataSourceRef | object | `{}` |  |
| persistence.data.enabled | bool | `true` |  |
| persistence.data.existingClaim | string | `""` |  |
| persistence.data.labels | object | `{}` |  |
| persistence.data.mountPath | string | `"/data"` |  |
| persistence.data.readOnly | bool | `false` |  |
| persistence.data.selector | object | `{}` |  |
| persistence.data.size | string | `"1Gi"` |  |
| persistence.data.storageClass | string | `""` |  |
| persistence.data.subPath | string | `""` |  |
| persistence.data.volumeName | string | `""` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| securityContext | object | `{}` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.automount | bool | `true` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.labels | object | `{}` |  |
| serviceAccount.name | string | `""` |  |
| services.main.annotations | object | `{}` |  |
| services.main.labels | object | `{}` |  |
| services.main.ports[0].name | string | `"http"` |  |
| services.main.ports[0].port | int | `80` |  |
| services.main.ports[0].protocol | string | `"TCP"` |  |
| services.main.ports[0].targetPort | string | `"http"` |  |
| services.main.type | string | `"ClusterIP"` |  |
| services.metrics.ports[0].name | string | `"metrics"` |  |
| services.metrics.ports[0].port | int | `9090` |  |
| services.metrics.ports[0].protocol | string | `"TCP"` |  |
| services.metrics.ports[0].targetPort | string | `"metrics"` |  |
| services.metrics.selector."app.kubernetes.io/component" | string | `"main"` |  |
| services.metrics.selector."app.kubernetes.io/name" | string | `"my-app"` |  |
| services.metrics.type | string | `"ClusterIP"` |  |
| tolerations | list | `[]` |  |
| volumes | list | `[]` |  |

