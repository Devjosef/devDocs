# Prometheus

## Introduction
Prometheus is an open-source systems monitoring and alerting toolkit originally built at SoundCloud. It is designed for reliability and scalability, making it a popular choice for monitoring cloud-native applications.

## Basic Syntax
```yaml
# Example of a basic Prometheus configuration
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['localhost:9090']
```

## Common Use Cases
- Monitoring system performance
- Collecting and querying metrics
- Setting up alerts for critical metrics
- Visualizing metrics with Grafana

## Advanced Features
- **Service Discovery**: Automatically discover targets to scrape.
- **Alertmanager**: Handle alerts sent by client applications.
- **PromQL**: Powerful query language for querying time series data.
- **Exporters**: Collect metrics from third-party systems.

## Code Snippets
### Service Discovery
```yaml
# Example of a Prometheus configuration with service discovery
scrape_configs:
  - job_name: 'kubernetes-apiservers'
    kubernetes_sd_configs:
      - role: endpoints
    relabel_configs:
      - source_labels: [__meta_kubernetes_namespace, __meta_kubernetes_service_name, __meta_kubernetes_endpoint_port_name]
        action: keep
        regex: default;kubernetes;https
```

### Alertmanager Configuration
```yaml
# Example of an Alertmanager configuration
global:
  resolve_timeout: 5m

route:
  group_by: ['alertname']
  group_wait: 30s
  group_interval: 5m
  repeat_interval: 12h
  receiver: 'email'

receivers:
  - name: 'email'
    email_configs:
      - to: 'your-email@example.com'
        from: 'alertmanager@example.com'
        smarthost: 'smtp.example.com:587'
        auth_username: 'alertmanager'
        auth_password: 'password'
```

### PromQL Query
```promql
# Example of a PromQL query to get CPU usage
rate(node_cpu_seconds_total{mode="idle"}[5m])
```

## Tips & Best Practices
- **Use Labels**: Use labels to add metadata to your metrics for better querying.
- **Alerting**: Set up alerts to monitor critical metrics and notify the right people.
- **Service Discovery**: Use service discovery to automatically discover targets.
- **Dashboards**: Use Grafana to create dashboards for visualizing metrics.
- **Exporters**: Use exporters to collect metrics from third-party systems.

## External Resources
- [Prometheus Official Documentation](https://prometheus.io/docs/)
- [Prometheus GitHub Repository](https://github.com/prometheus/prometheus)
- [PromQL Documentation](https://prometheus.io/docs/prometheus/latest/querying/basics/)
- [Awesome Prometheus](https://github.com/roaldnefs/awesome-prometheus)