# **Metric Collection**

The primary purpose of Prometheus is to **collect metric data** from systems and applications, store it, and make it available for analysis. Metrics are critical for observing system performance and health, such as CPU usage, memory consumption, and request response times. By collecting data in a time-series format, Prometheus provides detailed insights into the state of systems.

## **Pull Model**

Prometheus operates using a **pull model** for data collection. This means that Prometheus actively fetches data from systems at specified intervals. Each monitored application or system exposes its metrics via an HTTP endpoint (e.g., `/metrics`). Prometheus queries this endpoint and collects the exposed metrics.

- For example, to retrieve metrics from a web server, the server must provide a `/metrics` endpoint, which Prometheus regularly pulls data from.

## **Exporters**

In some cases, systems don’t natively expose metrics in a format compatible with Prometheus. Here, **exporters** act as intermediary tools that collect data from the system and convert it into Prometheus-compatible metrics.

- **Node Exporter**: Used to collect metrics at the server level, such as hardware and operating system data.
- **MySQL Exporter**: Gathers metrics from MySQL databases.
- **MSSQL Exporter**: Used to collect metrics from **Microsoft SQL Server**.

## **MSSQL Server Metric Collection**

To collect metrics from **Microsoft SQL Server (MSSQL)** with Prometheus, an MSSQL exporter is used. The MSSQL exporter provides various metrics to monitor the database’s performance and health, allowing for early detection of issues in the SQL Server.

- **Setup and Usage:**
  1. Install the **MSSQL Exporter**. This exporter connects to the MSSQL database and gathers relevant performance metrics.
  2. Once connected to the MSSQL server, the exporter collects data such as **CPU usage**, **database sizes**, **query durations**, and **memory usage**.
  3. The MSSQL exporter provides a `/metrics` endpoint that Prometheus queries at regular intervals to collect these metrics.

Commonly collected metrics include:

- **SQL Server CPU usage**
- **Number of active connections**
- **Query latencies**
- **Database I/O operations**
- **Lock and Deadlock events**

### **Configuration:**

The MSSQL Exporter is defined as a **scrape job** in the Prometheus configuration file. Here’s an example of a simple Prometheus configuration:

```yaml
scrape_configs:
  - job_name: 'mssql'
    static_configs:
      - targets: ['<MSSQL_exporter_IP>:9182']
```

In this configuration, Prometheus regularly queries the MSSQL Exporter’s `/metrics` endpoint to collect performance data from SQL Server. The exporter helps monitor SQL Server performance and health by gathering a wide range of useful metrics.

## Conclusion:

By using tools like the **MSSQL Exporter**, Prometheus can collect and monitor key metrics from Microsoft SQL Server, providing real-time insights into the database’s health and performance. This allows users to leverage Prometheus’ robust monitoring and alerting capabilities for SQL Server, enabling proactive management of database performance.
