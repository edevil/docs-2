# Prometheus

- Prometheus metrics are enabled by default in Envoy Proxy and Fyde Client
- The scrapping path is in the root of the endpoint `/`
- Ports can be customized in each component (check [Parameters](fyde_proxy_parameters.md))

## Examples

### Envoy Proxy Prometheus job configuration

- Add the following job to the existing prometheus configuration

```yaml
- job_name: fyde-envoy-proxy
  scrape_interval: 10s
  scrape_timeout:  5s
  metrics_path: /
  static_configs:
    - targets: ['fyde-envoy-proxy-1:9000']
```

### Envoy Proxy prometheus-operator Service Monitor

- Apply the following configuration
- Ensure that prometheus-operator is allowed to scrape that namespace

```yaml
---
apiVersion: monitoring.coreos.com/v1
kind: ServiceMonitor
metadata:
  labels:
    app: envoy-proxy
  name: envoy-proxy
spec:
  endpoints:
    - interval: 10s
      path: /
      port: prometheus-metrics
  namespaceSelector:
    matchNames:
      - fyde-proxy
  selector:
    matchLabels:
      app: envoy-proxy
```

- Also add the following to the corresponding service, if the service is deployed in kubernetes:

```yaml
    - name: prometheus-metrics
      protocol: TCP
      port: 9000
      targetPort: 9000
```
