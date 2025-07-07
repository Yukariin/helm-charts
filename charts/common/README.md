# Common Helm Chart Library

A comprehensive Helm chart library that provides reusable templates for Kubernetes resources. This library follows the DRY (Don't Repeat Yourself) principle and allows you to define all your Kubernetes resources in a single, maintainable location.

## Features

- **Single Loader**: One template file renders all Kubernetes resources
- **Multiple Deployments**: Support for multiple deployments with optional sidecars
- **Multiple Services**: Different service types and protocols
- **Flexible Persistence**: Configurable persistent volume claims
- **Ingress Support**: Multiple ingress configurations
- **Autoscaling**: Horizontal Pod Autoscaler support
- **Security**: Service accounts and security contexts
- **Comprehensive Configuration**: Environment variables, probes, resources, and more

## Usage

### 1. Add as Dependency

Add the common chart as a dependency in your `Chart.yaml`:

```yaml
dependencies:
  - name: common
    version: "0.1.0"
    repository: "https://yukariin.github.io/helm-charts"
```

### 2. Create Templates

Create a single template file `templates/all.yaml`:

```yaml
{{- include "common.loader" . }}
```

Optionally, create `templates/NOTES.txt`:

```yaml
{{- include "common.notes" . }}
```

### 3. Configure Values

Structure your `values.yaml` according to the common chart schema:

```yaml
# Global settings
nameOverride: ""
fullnameOverride: ""
imagePullSecrets: []

# Service account
serviceAccount:
  create: true
  automount: true
  annotations: {}
  name: ""

# Security contexts
podSecurityContext: {}
securityContext: {}

# Pod configuration
podAnnotations: {}
podLabels: {}
nodeSelector: {}
tolerations: []
affinity: {}
volumes: []

# Deployments (supports multiple)
deployments:
  main:
    replicaCount: 1
    image:
      repository: myapp
      pullPolicy: IfNotPresent
      tag: "latest"
    
    ports:
      - name: http
        containerPort: 8080
        protocol: TCP
    
    env:
      ENV_VAR: "value"
      COMPLEX_ENV:
        valueFrom:
          secretKeyRef:
            name: my-secret
            key: password
    
    livenessProbe:
      httpGet:
        path: /health
        port: http
    
    readinessProbe:
      httpGet:
        path: /ready
        port: http
    
    resources:
      limits:
        cpu: 500m
        memory: 512Mi
      requests:
        cpu: 250m
        memory: 256Mi
    
    autoscaling:
      enabled: false
      minReplicas: 1
      maxReplicas: 10
      targetCPUUtilizationPercentage: 80
    
    # Optional sidecars
    sidecars:
      - name: sidecar
        image:
          repository: sidecar-image
          tag: "latest"
        ports:
          - name: metrics
            containerPort: 9090
        env:
          SIDECAR_ENV: "value"

# Services (supports multiple)
services:
  main:
    type: ClusterIP
    ports:
      - name: http
        port: 80
        targetPort: http
        protocol: TCP
  
  metrics:
    type: ClusterIP
    ports:
      - name: metrics
        port: 9090
        targetPort: metrics
        protocol: TCP

# Ingress (supports multiple)
ingress:
  main:
    enabled: false
    className: ""
    annotations: {}
    hosts:
      - host: myapp.example.com
        paths:
          - path: /
            pathType: ImplementationSpecific
    tls: []

# Persistence (supports multiple volumes)
persistence:
  data:
    enabled: true
    size: 1Gi
    accessMode: ReadWriteOnce
    storageClass: ""
    mountPath: /data
  
  config:
    enabled: false
    size: 100Mi
    accessMode: ReadWriteOnce
    mountPath: /config
```

## Advanced Features

### Multiple Deployments

You can define multiple deployments for complex applications:

```yaml
deployments:
  frontend:
    replicaCount: 3
    image:
      repository: myapp/frontend
      tag: "v1.0.0"
    ports:
      - name: http
        containerPort: 3000
  
  backend:
    replicaCount: 2
    image:
      repository: myapp/backend
      tag: "v1.0.0"
    ports:
      - name: api
        containerPort: 8080
```

### Sidecar Containers

Add sidecar containers to your deployments:

```yaml
deployments:
  main:
    # ... main container config
    sidecars:
      - name: log-shipper
        image:
          repository: fluent/fluent-bit
          tag: "latest"
        volumeMounts:
          - name: logs
            mountPath: /var/log
        persistenceAccess:
          - logs  # Grant access to specific persistence volumes
```

### Environment Variables

Support for both simple and complex environment variables:

```yaml
deployments:
  main:
    env:
      # Simple string value
      SIMPLE_VAR: "value"
      
      # Complex object (valueFrom, etc.)
      SECRET_VAR:
        valueFrom:
          secretKeyRef:
            name: my-secret
            key: password
      
      # ConfigMap reference
      CONFIG_VAR:
        valueFrom:
          configMapKeyRef:
            name: my-config
            key: config-value
```

## Template Functions

The common chart provides several helper functions:

- `common.name`: Generate the application name
- `common.fullname`: Generate the full application name
- `common.chart`: Generate the chart label
- `common.labels`: Generate standard labels
- `common.selectorLabels`: Generate selector labels
- `common.serviceAccountName`: Generate service account name
- `common.deploymentName`: Generate deployment name
- `common.serviceName`: Generate service name
- `common.pvcName`: Generate PVC name

## Migration from Individual Templates

To migrate existing charts:

1. Add the common chart dependency
2. Replace all template files with `templates/all.yaml` containing `{{- include "common.loader" . }}`
3. Update `values.yaml` to match the common chart structure
4. Remove individual template files (deployment.yaml, service.yaml, etc.)
5. Update `templates/NOTES.txt` to use `{{- include "common.notes" . }}`

## Version

Current version: 0.1.0

## License

This chart is licensed under the same terms as the parent repository.
