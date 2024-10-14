# Prometheus and Grafana Integration

This project sets up **Prometheus** and **Grafana** for effective monitoring and visualization of system metrics. By integrating these two powerful tools, you can gain valuable insights into your application's performance and health.

## Overview

- **Prometheus**: An open-source monitoring and alerting toolkit that collects and stores metrics in a time-series database.
- **Grafana**: An open-source analytics platform that visualizes metrics from various data sources, including Prometheus.

## Setup Instructions

### Prerequisites

- Windows Server 2022 (or supported OS)
- Administrative access

### Installation Steps

1. **Install Prometheus**:

   - Download from the [Prometheus website](https://prometheus.io/download/#prometheus).
   - Configure `prometheus.yml` to scrape metrics.
   - Run Prometheus using:
     ```bash
     prometheus.exe --config.file=prometheus.yml
     ```
2. **Install Windows Exporter**:

   - Download the [Windows Exporter](https://github.com/prometheus-community/windows_exporter/releases).
   - Follow the installation prompts to set it up.
3. **Install Grafana**:

   - Download Grafana from the [Grafana website](https://grafana.com/grafana/download).
   - Start Grafana, accessible at `http://localhost:3000`.
4. **Configure Grafana**:

   - Log in with default credentials (admin/admin).
   - Add Prometheus as a data source (URL: `http://localhost:9090`).
   - Create dashboards by selecting metrics with PromQL queries.
5. **Optional - Set Up Alerts**:

   - Configure alerts in Grafana to notify you of critical issues.
   -
