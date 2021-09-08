# selenium-grid

This is a selenium grid helm chart.

![Version: 0.1.1](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.0.0-rc-1-20210902](https://img.shields.io/badge/AppVersion-4.0.0--rc--1--20210902-informational?style=flat-square)

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
| chrome.screenDepth | int | `nil` | Chrome node screen depth configuration |
| chrome.screenDpi | int | `nil` | Chrome node screen dpi configuration |
| chrome.screenHeight | int | `1080` | (int) Chrome node screen heigth configuration |
| chrome.screenWidth | int | `1920` |  |
| chrome.tag | string | `"4.0.0-rc-1-20210902"` | Chrome node tag |
| chrome.vncPort | int | `6900` | Chrome node vnc port |
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
| router.ingress.annotations | string | `nil` |  |
| router.ingress.enabled | bool | `true` |  |
| router.ingress.hosts[0] | string | `"selenium-grid.kube.home"` |  |
| router.ingress.ingressClassName | string | `"nginx"` |  |
| router.ingress.path | string | `"/"` |  |
| router.loadBalancerSourceRanges | list | `[]` |  |
| router.port | int | `4444` |  |
| router.repository | string | `"selenium/router"` |  |
| router.serviceType | string | `"ClusterIP"` |  |
| router.tag | string | `"4.0.0-rc-1-20210902"` |  |
| sessions.mapPort | int | `5556` | define the selenium sessions map port |
| sessions.repository | string | `"selenium/sessions"` |  |
| sessions.tag | string | `"4.0.0-rc-1-20210902"` |  |
| sessionsQueue.queuePort | int | `5559` | define the selenium sessions queue port |
| sessionsQueue.repository | string | `"selenium/session-queue"` |  |
| sessionsQueue.tag | string | `"4.0.0-rc-1-20210902"` |  |
