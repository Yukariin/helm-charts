# freshrss

![Version: 0.2.0](https://img.shields.io/badge/Version-0.2.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.26.3](https://img.shields.io/badge/AppVersion-1.26.3-informational?style=flat-square)

A FreshRSS Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://bjw-s-labs.github.io/helm-charts | common | 4.1.2 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllers.main.containers.main.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.main.containers.main.image.repository | string | `"freshrss/freshrss"` | image repository |
| controllers.main.containers.main.image.tag | string | `"1.26.3"` | image tag |
| controllers.main.containers.main.probes.liveness | object | `{"path":"/i/","type":"HTTP"}` | Configures liveness probe |
| controllers.main.containers.main.probes.readiness | object | `{"path":"/i/","type":"HTTP"}` | Configures readiness probe |
| controllers.main.strategy | string | `"Recreate"` | Set the controller upgrade strategy |
| controllers.updater.containers.main.args[0] | string | `"www-data"` |  |
| controllers.updater.containers.main.args[1] | string | `"-s"` |  |
| controllers.updater.containers.main.args[2] | string | `"/bin/sh"` |  |
| controllers.updater.containers.main.args[3] | string | `"-c"` |  |
| controllers.updater.containers.main.args[4] | string | `"php /var/www/FreshRSS/app/actualize_script.php"` |  |
| controllers.updater.containers.main.command | string | `"/usr/bin/su"` |  |
| controllers.updater.containers.main.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| controllers.updater.containers.main.image.repository | string | `"freshrss/freshrss"` | image repository |
| controllers.updater.containers.main.image.tag | string | `"1.26.3"` | image tag |
| controllers.updater.cronjob.backoffLimit | int | `3` |  |
| controllers.updater.cronjob.concurrencyPolicy | string | `"Forbid"` |  |
| controllers.updater.cronjob.failedJobsHistory | int | `1` |  |
| controllers.updater.cronjob.schedule | string | `"*/20 * * * *"` |  |
| controllers.updater.cronjob.startingDeadlineSeconds | int | `30` |  |
| controllers.updater.cronjob.successfulJobsHistory | int | `1` |  |
| controllers.updater.cronjob.suspend | bool | `false` |  |
| controllers.updater.type | string | `"cronjob"` |  |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.data.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.data.globalMounts[0].path | string | `"/var/www/FreshRSS/data"` |  |
| persistence.data.retain | bool | `true` |  |
| persistence.data.size | string | `"500Mi"` |  |
| persistence.extensions.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.extensions.globalMounts[0].path | string | `"/var/www/FreshRSS/extensions"` |  |
| persistence.extensions.size | string | `"500Mi"` |  |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

