# selenium-grid

This is a selenium grid helm chart.

![Version: 0.3.0](https://img.shields.io/badge/Version-0.3.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.0.0-rc-1-20210902](https://img.shields.io/badge/AppVersion-4.0.0--rc--1--20210902-informational?style=flat-square)

## Selenium grid helm chart installatio

To install the chart run the following commands:

```console
$ helm repo add helm-selenium https://frste.github.io/helm-charts
$ helm repo update
$ helm install my-selenium-grid helm-selenium/selenium
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| chrome.autoscaler.enabled | bool | `false` |  |
| chrome.autoscaler.maxReplicaCount | int | `4` |  |
| chrome.autoscaler.minReplicaCount | int | `0` |  |
| chrome.enabled | bool | `true` | Enable chrome node deployment |
| chrome.replicas | int | `1` | Set chrome node replica count |
| chrome.repository | string | `"selenium/node-chrome"` | Chrome node repository |
| chrome.resources | object | `{"limits":{"cpu":"1","memory":"1Gi"},"requests":{"cpu":"1","memory":"1Gi"}}` | Configure chrome node resource requests/limits |
| chrome.screenDepth | int | `nil` | Chrome node screen depth configuration |
| chrome.screenDpi | int | `nil` | Chrome node screen dpi configuration |
| chrome.screenHeight | int | `1080` | (int) Chrome node screen heigth configuration |
| chrome.screenWidth | int | `1920` |  |
| chrome.seNodeGridUrl | string | `"http://selenium-grid.kube.home"` | Configure node grid url rewrite adress |
| chrome.tag | string | `"4.0.0-rc-1-20210902"` | Chrome node tag |
| chrome.vncNoPassword | bool | `true` | VNC password can be disabled to enable vnc web view in grid |
| chrome.vncPort | int | `5900` | Chrome node vnc port |
| chrome.vncTargetPort | int | `5900` | Chrome node vnc target port |
| component | string | `"selenium-grid-4"` |  |
| distributor.distributorPort | int | `5553` | define distributor port |
| distributor.repository | string | `"selenium/distributor"` |  |
| distributor.tag | string | `"4.0.0-rc-1-20210902"` |  |
| eventBus.port | int | `5557` | define the event bus port |
| eventBus.publishPort | int | `4442` | define event bus publish port |
| eventBus.repository | string | `"selenium/event-bus"` |  |
| eventBus.subscribePort | int | `4443` | define event bus subscribe port |
| eventBus.tag | string | `"4.0.0-rc-1-20210902"` |  |
| router.ingress.annotations | string | `nil` | define custom annotations for ingress. Sample annotations are needed to use vnc with an nginx.org ingress |
| router.ingress.enabled | bool | `false` |  |
| router.ingress.hosts[0] | string | `"selenium-grid.kube.home"` |  |
| router.ingress.ingressClassName | string | `"nginx"` |  |
| router.ingress.path | string | `"/"` |  |
| router.livenessProbe | object | `{"failureThreshold":3,"httpGet":{"path":"/","port":"web"},"initialDelaySeconds":15,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":5}` | Define router liveness probe |
| router.loadBalancerSourceRanges | list | `[]` |  |
| router.port | int | `4444` | Define router service port |
| router.portName | string | `"web"` | Define router service port name |
| router.readinessProbe | object | `{"exec":{"command":["/bin/sh","-c","curl -sSL \"http://localhost:4444/wd/hub/status\" 2>&1 | jq -e \".value.ready\"==true"]},"failureThreshold":1,"initialDelaySeconds":15,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":5}` | Define router readiness probe |
| router.repository | string | `"selenium/router"` |  |
| router.resources | object | `{"limits":null,"requests":null}` | Configure router resource requests/limits |
| router.serviceType | string | `"ClusterIP"` |  |
| router.startupProbe | object | `{"exec":{"command":["/bin/sh","-c","curl -sSL \"http://localhost:4444/wd/hub/status\" 2>&1 | jq -e \".value.ready\"==true"]},"failureThreshold":30,"periodSeconds":10}` | Define router startup probe |
| router.tag | string | `"4.0.0-rc-1-20210902"` |  |
| sessions.mapPort | int | `5556` | define the selenium sessions map port |
| sessions.repository | string | `"selenium/sessions"` |  |
| sessions.tag | string | `"4.0.0-rc-1-20210902"` |  |
| sessionsQueue.queuePort | int | `5559` | define the selenium sessions queue port |
| sessionsQueue.repository | string | `"selenium/session-queue"` |  |
| sessionsQueue.tag | string | `"4.0.0-rc-1-20210902"` |  |
