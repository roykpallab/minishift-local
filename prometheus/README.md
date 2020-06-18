##  Prometheus and Grafana on Openshift Origin

### Deploy Prometheus & Grafana
```sh
oc new-project prometheus-example   #choose a namespace
oc new-app google/cadvisor
oc new-app prom/prometheus
oc expose service cadvisor
oc expose service prometheus
oc create configmap prom-config-example --from-file=prometheus.yml
oc set volume dc/prometheus --add --name=prom-config-example-volume -m /etc/prometheus -t configmap --configmap-name=prom-config-example
oc new-app grafana/grafana

```










