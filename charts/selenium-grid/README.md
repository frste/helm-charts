# selenium-grid-4

This is a selenium grid helm chart.

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.0.0-rc-1-20210902](https://img.shields.io/badge/AppVersion-4.0.0--rc--1--20210902-informational?style=flat-square)

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
| chrome.enabled | bool | `false` | Enable chrome node deployment |
| chrome.replicas | int | `1` | Set chrome node replica count |
| chrome.repository | string | `"selenium/node-chrome"` | Chrome node repository |
| chrome.screenDepth | int | `nil` | Chrome node screen depth configuration |
| chrome.screenDpi | int | `nil` | Chrome node screen dpi configuration |
| chrome.screenHeight | int | `1080` | (int) Chrome node screen heigth configuration |
| chrome.screenWidth | int | `1920` |  |
| chrome.tag | string | `"4.0.0-rc-1-20210902"` | Chrome node tag |
| component | string | `"selenium-grid-4"` |  |
| distributor.port | int | `5553` |  |
| distributor.repository | string | `"selenium/distributor"` |  |
| distributor.servicePort | int | `5553` |  |
| distributor.tag | string | `"4.0.0-rc-1-20210902"` |  |
| eventBus.repository | string | `"selenium/event-bus"` |  |
| eventBus.tag | string | `"4.0.0-rc-1-20210902"` |  |
| router.loadBalancerSourceRanges | list | `[]` |  |
| router.port | int | `4444` |  |
| router.port1 | int | `4442` |  |
| router.port2 | int | `4443` |  |
| router.repository | string | `"selenium/router"` |  |
| router.servicePort | int | `4444` |  |
| router.serviceType | string | `"ClusterIP"` |  |
| router.tag | string | `"4.0.0-rc-1-20210902"` |  |
| sessions.repository | string | `"selenium/sessions"` |  |
| sessions.tag | string | `"4.0.0-rc-1-20210902"` |  |
| sessionsQueue.repository | string | `"selenium/session-queue"` |  |
| sessionsQueue.tag | string | `"4.0.0-rc-1-20210902"` |  |
