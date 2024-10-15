# Alert Alarm, Sending Mail / Notify To ...

When you set up an alarm in Prometheus and it exceeds the specified thresholds, Prometheus can notify you through various alerting mechanisms. Here's how the alarm system works and how notifications are sent:

### 1. **Alarm Rule Definition**

First, you define an alerting rule in your configuration file (e.g., `alert.rules.yml`). Here's an example of how you might define an alert for high CPU usage:

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

### 2. **Alert Evaluation**

Prometheus evaluates alert rules at specified intervals (defined in `prometheus.yml`, under the `global` settings). If the alert condition is met (e.g., CPU usage exceeds 80%), the alert is triggered.

### 3. **Alert State Change**

Once triggered, the alert changes its state from "pending" to "firing." This transition indicates that the alert condition is currently true.

### 4. **Alert Notifications via Alertmanager**

To send notifications, Prometheus typically works with **Alertmanager**, a component designed to handle alerts. Here’s how it works:

- **Configuration of Alertmanager:** In your Prometheus configuration file (`prometheus.yml`), you specify the Alertmanager’s address. For example:

  ```yaml
  alerting:
    alertmanagers:
      - static_configs:
          - targets:
            - 'localhost:9093'  # Address of Alertmanager
  ```
- **Notification Channels:** In the Alertmanager configuration file (`alertmanager.yml`), you define notification channels (e.g., email, Slack, PagerDuty). Here's an example configuration for email notifications:

  ```yaml
  global:
    smtp_smarthost: 'smtp.example.com:587'
    smtp_from: 'alert@example.com'
    smtp_auth_username: 'your_username'
    smtp_auth_password: 'your_password'

  route:
    group_by: ['alertname']
    group_wait: 30s
    group_interval: 5m
    repeat_interval: 1h
    receiver: 'email-notifications'

  receivers:
    - name: 'email-notifications'
      email_configs:
        - to: 'your_email@example.com'
          from: 'alert@example.com'
          subject: '[Alert] {{ .Alertname }}'
  ```

### 5. **Alert Notification Process**

Once the alert is in the "firing" state, Alertmanager processes it according to the configured routing rules. Here’s what happens:

- **Notification Groups:** Alerts can be grouped by labels, which reduces alert fatigue by bundling similar alerts into a single notification.
- **Alert Sending:** Alertmanager sends notifications through the configured channels. For instance, if you set up email notifications, an email will be sent to the specified address with details about the alert.

### 6. **Alert Resolution**

When the alert condition resolves (e.g., CPU usage falls back below 80%), Prometheus updates the alert state back to "resolved." Alertmanager can also send a notification indicating that the alert condition has been cleared, depending on your configuration.

### Summary

To summarize, when you set an alert in Prometheus, it continuously evaluates the defined conditions. If the conditions exceed the specified thresholds, the alert is triggered. Alertmanager then takes care of notifying you through your chosen communication channels, such as email or messaging platforms. This setup allows you to quickly respond to issues in your systems, improving reliability and performance.
