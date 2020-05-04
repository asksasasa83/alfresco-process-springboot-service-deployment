alfresco-process-springboot-service
===================================
A Helm chart for a generic Alfresco Process/Activiti Spring Boot based microservice

Current chart version is `2.2.0`

Source code can be found [here](https://www.alfresco.com)

## Chart Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://activiti.github.io/activiti-cloud-helm-charts | common | 1.1.36 |

## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| db.ddlAuto | string | `nil` |  |
| db.driver | string | `nil` |  |
| db.generateDdl | string | `nil` |  |
| db.password | string | `nil` |  |
| db.platform | string | `nil` |  |
| db.uri | string | `nil` |  |
| db.username | string | `nil` |  |
| extraContainers | string | `""` |  |
| extraEnv | string | `"# - name: ACT_KEYCLOAK_URL\n#   valueFrom:\n#     configMapKeyRef:\n#       name: {{ .Release.Name }}-keycloak-http\n#       key: expose-keycloak-service-key\n"` |  |
| extraInitContainers | string | `""` |  |
| extraVolumeMounts | string | `""` |  |
| extraVolumes | string | `""` |  |
| global.gateway.host | string | `""` |  |
| global.keycloak.name | string | `"keycloak"` |  |
| global.keycloak.realm | string | `""` |  |
| global.keycloak.resource | string | `""` |  |
| global.keycloak.service.port | int | `80` |  |
| global.keycloak.service.type | string | `"http"` |  |
| global.keycloak.url | string | `""` |  |
| global.rabbitmq.host.value | string | `""` |  |
| global.rabbitmq.password.value | string | `"guest"` |  |
| global.rabbitmq.username.value | string | `"guest"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"activiti/example-runtime-bundle"` |  |
| image.tag | string | `"7.0.0.SR1"` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hostName | string | `nil` |  |
| ingress.path | string | `"/rb-my-app"` |  |
| ingress.tls | string | `nil` |  |
| ingress.tlsSecret | string | `nil` |  |
| init.image.pullPolicy | string | `"IfNotPresent"` |  |
| init.image.repository | string | `"alpine"` |  |
| init.image.tag | float | `3.8` |  |
| javaOpts.other | string | `"-XX:+UnlockExperimentalVMOptions -Dsun.zip.disableMemoryMapping=true -XX:+UseParallelGC -XX:MinHeapFreeRatio=5 -XX:MaxHeapFreeRatio=10 -XX:GCTimeRatio=4 -XX:AdaptiveSizePolicyWeight=90"` |  |
| javaOpts.xms | string | `"512m"` |  |
| javaOpts.xmx | string | `"2048m"` |  |
| livenessProbe.failureThreshold | int | `4` |  |
| livenessProbe.initialDelaySeconds | int | `60` |  |
| livenessProbe.periodSeconds | int | `15` |  |
| livenessProbe.successThreshold | int | `1` |  |
| livenessProbe.timeoutSeconds | int | `4` |  |
| postgres.enabled | bool | `false` |  |
| postgres.name | string | `"postgres"` |  |
| postgres.password | string | `nil` |  |
| postgres.port | int | `5432` |  |
| postgres.username | string | `"postgres"` |  |
| probePath | string | `"/actuator/health"` |  |
| rabbitmq.enabled | bool | `true` |  |
| rbac.create | bool | `true` |  |
| readinessProbe.failureThreshold | int | `3` |  |
| readinessProbe.initialDelaySeconds | int | `20` |  |
| readinessProbe.periodSeconds | int | `15` |  |
| readinessProbe.successThreshold | int | `1` |  |
| readinessProbe.timeoutSeconds | int | `3` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | int | `2` |  |
| resources.limits.memory | string | `"2048Mi"` |  |
| resources.requests.cpu | string | `"200m"` |  |
| resources.requests.memory | string | `"512Mi"` |  |
| securityContext | string | `"# to specify docker daemon access\n# privileged: true\n"` |  |
| service.annotations."fabric8.io/expose" | string | `"false"` |  |
| service.externalPort | int | `80` |  |
| service.internalPort | int | `8080` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.create | bool | `true` |  |
| terminationGracePeriodSeconds | int | `20` |  |
