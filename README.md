# helm-starter
Helm Starter

## Install

```sh
git clone https://github.com/plimble/helm-starter.git $(helm home)/starters/default
```


## Usage

```sh
helm create -p default myChart
```


## Default Values

```yaml
# Default values for helm-starter.
# This is a YAML-formatted file.
# Declare variables to be passed into your templates.

# Override chart name
nameOverride: ''

replicaCount: 1

image:
  repository: nginx
  tag: stable
  pullPolicy: Always

alwaysUpdate: false

annotations: {}

podAnnotations: {}

imagePullSecrets: []
  # - name: gitlab-registry-credential

args: []
  # - /bin/sh
  # - -c

env: []
  # - name: ENV1
  #   value: XXXXX
  # - name: ENV2
  #   value: XXXXXX

envFrom: []
  # - name: env-config

configMaps: []
  # - name: "config"
  #   mountPath: "/firebase"
  #   configName: config-from-outside
  #   data:
  #     firebaseCredentials.json : |-
  #       {"test": "test"}

secrets: []
  # - name: "secret"
  #   mountPath: "/tls"
  #   type: "kubernetes.io/tls"
  #   secretName: secret-from-outside
  #   data:
  #     tls.crt: '132'
  #     tls.key: '132'

resources: {}
  # We usually recommend not to specify default resources and to leave this as a conscious
  # choice for the user. This also increases chances charts run on environments with little
  # resources, such as Minikube. If you do want to specify resources, uncomment the following
  # lines, adjust them as necessary, and remove the curly braces after 'resources:'.
  # limits:
  #  cpu: 100m
  #  memory: 128Mi
  # requests:
  #  cpu: 100m
  #  memory: 128Mi

# Check container is alive and healthy
# If not, the kubelet kills the Container and restarts it.
livenessProbe: {}
  # httpGet:
  #   path: /
  #   port: 80 or port name
  # initialDelaySeconds: 5
  # periodSeconds: 10
  # failureThreshold: 3

# Ensure the traffic does not reach a container which is not ready for it,
readinessProbe: {}
  # tcpSocket:
    # port: 8080
  # initialDelaySeconds: 5
  # periodSeconds: 10
  # failureThreshold: 3

nodeSelector: {}

tolerations: []

affinity: {}

service:
  enabled: false
  annotations: {}
  type: ClusterIP
  ports: []
    # - name: "http"
    #   port: 80
    #   targetPort: 8080
    # - name: "https"
    #   port: 443

ingress:
  enabled: false
  annotations: {}
    # kubernetes.io/ingress.class: nginx
    # kubernetes.io/tls-acme: "true"
  hosts: []
    # - host: chart-example.local
    #   path: /
    #   servicePort: 8080
  tls: []
  #  - secretName: chart-example-tls
  #    hosts:
  #      - chart-example.local
```