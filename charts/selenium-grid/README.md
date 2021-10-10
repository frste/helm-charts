# selenium-grid

This is a selenium grid helm chart.

![Version: 0.4.6](https://img.shields.io/badge/Version-0.4.6-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.0.0-rc-2-20210930](https://img.shields.io/badge/AppVersion-4.0.0--rc--2--20210930-informational?style=flat-square)

## Selenium grid helm chart installation

To install the chart run the following commands:

```console
$ helm repo add helm-selenium https://frste.github.io/helm-charts
$ helm repo update
$ helm install my-selenium-grid helm-selenium/selenium
```

## General

This Chart is based on the SeleniumHQ k8s deployment Manifest https://github.com/SeleniumHQ/docker-selenium/blob/trunk/k8s-deployment-full-grid.yaml.
The base Manifest has been extended with different objects.

## Ingress

Using this Helm Chart it's possible to define an Ingress.

## Scaling

This Chart uses Keda Selenium Grid Scaler to scale the Node pods https://keda.sh/docs/2.4/scalers/selenium-grid-scaler/

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| chrome.annotations | string | `nil` | Define chrome node pod annotations |
| chrome.autoscaler.enabled | bool | `false` |  |
| chrome.autoscaler.maxReplicaCount | int | `4` |  |
| chrome.autoscaler.minReplicaCount | int | `0` |  |
| chrome.enabled | bool | `true` | Enable chrome node deployment |
| chrome.javaOpts | string | `nil` | Configure chrome JAVA_OPTS |
| chrome.preStop | object | `{"enabled":true}` | Enable preStop to drain node directly on replica change |
| chrome.replicas | int | `1` | Set chrome node replica count |
| chrome.repository | string | `"selenium/node-chrome"` | Chrome node repository |
| chrome.resources | object | `{"limits":{"cpu":"1","memory":"1Gi"},"requests":{"cpu":"1","memory":"1Gi"}}` | Configure chrome node resource requests/limits |
| chrome.screenDepth | int | `nil` | Chrome node screen depth configuration |
| chrome.screenDpi | int | `nil` | Chrome node screen dpi configuration |
| chrome.screenHeight | int | `1080` | (int) Chrome node screen heigth configuration |
| chrome.screenWidth | int | `1920` |  |
| chrome.seNodeGridUrl | string | `"http://selenium-grid.kube.home"` | Configure node grid url rewrite adress |
| chrome.seOpts | string | `nil` | Configure chrome SE_OPTS |
| chrome.tag | string | `"4.0.0-rc-2-20210930"` | Chrome node tag |
| chrome.vncNoPassword | bool | `true` | VNC password can be disabled to enable vnc web view in grid |
| chrome.vncPort | int | `5900` | Chrome node vnc port |
| chrome.vncTargetPort | int | `5900` | Chrome node vnc target port |
| chrome.volumeMounts | list | `[{"mountPath":"/dev/shm","name":"dshm"}]` | Configure chrome node volume mounts |
| chrome.volumes | list | `[{"emptyDir":{"medium":"Memory"},"name":"dshm"}]` | Configure chrome node volume mounts |
| component | string | `"selenium-grid-4"` |  |
| distributor.annotations | string | `nil` | Define distributor pod annotations |
| distributor.distributorPort | int | `5553` | define distributor port |
| distributor.javaOpts | string | `nil` | Configure distributor JAVA_OPTS |
| distributor.repository | string | `"selenium/distributor"` |  |
| distributor.tag | string | `"4.0.0-rc-2-20210930"` |  |
| edge.annotations | string | `nil` | Define edge node pod annotations |
| edge.autoscaler.enabled | bool | `false` |  |
| edge.autoscaler.maxReplicaCount | int | `4` |  |
| edge.autoscaler.minReplicaCount | int | `0` |  |
| edge.enabled | bool | `true` | Enable edge node deployment |
| edge.javaOpts | string | `nil` | Configure edge JAVA_OPTS |
| edge.preStop | object | `{"enabled":true}` | Enable preStop to drain node directly on replica change |
| edge.replicas | int | `0` | Set edge node replica count |
| edge.repository | string | `"selenium/node-edge"` | Edge node repository |
| edge.resources | object | `{"limits":{"cpu":"1","memory":"1Gi"},"requests":{"cpu":"1","memory":"1Gi"}}` | Configure Edge node resource requests/limits |
| edge.screenDepth | int | `nil` | Edge node screen depth configuration |
| edge.screenDpi | int | `nil` | Edge node screen dpi configuration |
| edge.screenHeight | int | `1080` | (int) Edge node screen heigth configuration |
| edge.screenWidth | int | `1920` |  |
| edge.seNodeGridUrl | string | `"http://selenium-grid.kube.home"` | Configure node grid url rewrite adress |
| edge.seOpts | string | `nil` | Configure edge SE_OPTS |
| edge.tag | string | `"4.0.0-rc-2-20210930"` | Edge node tag |
| edge.vncNoPassword | bool | `true` | VNC password can be disabled to enable vnc web view in grid |
| edge.vncPort | int | `6901` | Edge node vnc port |
| edge.vncTargetPort | int | `5900` | Edge node vnc target port |
| edge.volumeMounts | list | `[{"mountPath":"/dev/shm","name":"dshm"}]` | Configure edge node volume mounts |
| edge.volumes | list | `[{"emptyDir":{"medium":"Memory"},"name":"dshm"}]` | Configure edge node volume mounts |
| eventBus.annotations | string | `nil` | Define event bus pod annotations |
| eventBus.javaOpts | string | `nil` | Configure event bus JAVA_OPTS |
| eventBus.port | int | `5557` | define the event bus port |
| eventBus.publishPort | int | `4442` | define event bus publish port |
| eventBus.repository | string | `"selenium/event-bus"` |  |
| eventBus.subscribePort | int | `4443` | define event bus subscribe port |
| eventBus.tag | string | `"4.0.0-rc-2-20210930"` |  |
| router.annotations | string | `nil` | Define router pod annotations |
| router.ingress.annotations | string | `nil` | define custom annotations for ingress. Sample annotations are needed to use vnc with an nginx.org ingress |
| router.ingress.enabled | bool | `false` |  |
| router.ingress.hosts[0] | string | `"selenium-grid.kube.home"` |  |
| router.ingress.ingressClassName | string | `"nginx"` |  |
| router.ingress.path | string | `"/"` |  |
| router.javaOpts | string | `nil` | Configure router JAVA_OPTS |
| router.livenessProbe | object | `{"failureThreshold":3,"httpGet":{"path":"/","port":"web"},"initialDelaySeconds":15,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":5}` | Define router liveness probe |
| router.loadBalancerSourceRanges | list | `[]` |  |
| router.port | int | `4444` | Define router service port |
| router.portName | string | `"web"` | Define router service port name |
| router.readinessProbe | object | `{"failureThreshold":1,"httpGet":{"path":"/","port":"web"},"initialDelaySeconds":15,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":5}` | Define router readiness probe |
| router.repository | string | `"selenium/router"` |  |
| router.resources | object | `{"limits":null,"requests":null}` | Configure router resource requests/limits |
| router.seOpts | string | `nil` | Configure router SE_OPTS |
| router.serviceType | string | `"ClusterIP"` |  |
| router.startupProbe | object | `{"failureThreshold":30,"httpGet":{"path":"/","port":"web"},"periodSeconds":10}` | Define router startup probe |
| router.tag | string | `"4.0.0-rc-2-20210930"` |  |
| sessions.annotations | string | `nil` | Define sessions pod annotations |
| sessions.javaOpts | string | `nil` | Configure sessions map JAVA_OPTS |
| sessions.mapPort | int | `5556` | define the selenium sessions map port |
| sessions.repository | string | `"selenium/sessions"` |  |
| sessions.tag | string | `"4.0.0-rc-2-20210930"` |  |
| sessionsQueue.annotations | string | `nil` | Define sessions-queue pod annotations |
| sessionsQueue.javaOpts | string | `nil` | Configure sessions queue JAVA_OPTS |
| sessionsQueue.queuePort | int | `5559` | define the selenium sessions queue port |
| sessionsQueue.repository | string | `"selenium/session-queue"` |  |
| sessionsQueue.requestTimeout | string | `nil` | define a custom session request timeout -- @default 300 |
| sessionsQueue.retryInterval | string | `nil` | define a custom session retry interval -- @default 5 |
| sessionsQueue.tag | string | `"4.0.0-rc-2-20210930"` |  |
