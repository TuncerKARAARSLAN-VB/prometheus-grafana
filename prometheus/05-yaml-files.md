# Yaml Files

Prometheus is an open-source monitoring and alerting system that uses YAML (YAML Ain't Markup Language) files for its configuration. Below is an overview of the types of Prometheus YAML files and what each one is used for.

### 1. **Prometheus Configuration File (prometheus.yml)**

**Purpose:**
This file defines how Prometheus operates and which resources it should monitor. It contains the following key components:

- **Global Settings:**
  This section includes global settings, such as the scrape interval (how often to collect data).

  ```yaml
  global:
    scrape_interval: 15s  # Data collection interval
  ```
- **Scrape Configurations:**
  Defines which targets to monitor. Each target pulls data from an HTTP endpoint.

  ```yaml
  scrape_configs:
    - job_name: 'node_exporter'
      static_configs:
        - targets: ['localhost:9100']  # Target URLs
  ```
- **Alerting Rules:**
  Contains rules for generating alerts. Prometheus can send alerts when certain conditions are met.

### 2. **Alert Rule Files (alert.rules.yml)**

**Purpose:**
These files enable Prometheus to send alerts based on specific conditions. Alerts are used to detect anomalies in the system.

```yaml
groups:
  - name: example_alerts
    rules:
      - alert: HighCPUUsage
        expr: sum(rate(cpu_usage_seconds_total[5m])) by (instance) > 0.8
        for: 5m
        labels:
          severity: critical
        annotations:
          summary: "High CPU Usage Detected"
          description: "CPU usage is above 80% for more than 5 minutes."
```

### 3. **Recording Rule Files (recording.rules.yml)**

**Purpose:**
These files pre-calculate and store the results of frequently used or complex queries. This improves query performance and enables faster results.

```yaml
groups:
  - name: example_recording_rules
    rules:
      - record: job:cpu_usage:sum
        expr: sum(rate(cpu_usage_seconds_total[5m])) by (job)
```

### 4. **Service Monitor Files (service-monitor.yml)** (For Kubernetes)

**Purpose:**
Used to facilitate monitoring of specific services in a Kubernetes environment. ServiceMonitors automatically create configurations for targeted services.

```yaml
apiVersion: monitoring.coreos.com/v1
kind: ServiceMonitor
metadata:
  name: example-service-monitor
  labels:
    app: my-app
spec:
  selector:
    matchLabels:
      app: my-app
  endpoints:
    - port: web
      interval: 30s
```

### Important Note

Whenever changes are made to any Prometheus YAML configuration files, it is essential to restart the Prometheus service for the changes to take effect. This ensures that Prometheus loads the new configurations and operates as intended.

### Summary

Prometheus YAML files are crucial for configuring the system, determining which metrics to monitor, establishing alert rules, and setting up recording rules. With these configurations, Prometheus simplifies the monitoring and analysis of system resources, as well as detecting anomalies and sending alerts about such situations. This helps system administrators and developers quickly identify and resolve issues.
