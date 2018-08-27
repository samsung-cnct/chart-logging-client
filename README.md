# chart-logging-central

[![Build Status](https://jenkins.migrations.cnct.io/buildStatus/icon?job=pipeline-client-logging/master)](https://jenkins.migrations.cnct.io/job/pipeline-client-logging/job/master)

[`chart-logging-central`](https://github.com/samsung-cnct/chart-logging-central) and [`chart-logging-client`](https://github.com/samsung-cnct/chart-logging-client) (this chart) implement our
central logging solution for Kubernetes clusters. These replace the deprecated [`chart-logging`](https://github.com/samsung-cnct/chart-logging).

This system will collect Kubernetes logs and events with fluentbit and eventrouter, enrich them with Kubernetes metadata and send them to the central-logging system. There they will be saved in an elasticsearch data store and made available for visualization and querying with kibana.  Curator will delete old indices after two weeks. 

## How to install on running Kubernetes cluster with [helm](https://github.com/kubernetes/helm/blob/master/docs/install.md)
Ensure that you have helm and [tiller](https://docs.helm.sh/using_helm/) installed. 

### From our chart repository
``` 
helm repo add cnct https://charts.migrations.cnct.io
helm repo update
helm install cnct/logging-client
```

## Assets 
#### Fluent-bit for log collection 
- [Docs](https://fluentbit.io/)
- [Chart](https://github.com/samsung-cnct/chart-fluent-bit)

#### Eventrouter to collect kubernetes apiserver events 
- [Chart](https://github.com/samsung-cnct/chart-eventrouter)

### Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D