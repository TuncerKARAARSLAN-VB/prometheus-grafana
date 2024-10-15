# Various Exporters

| **Exporter**               | **Description**                                                                                                                                     |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Node Exporter**          | Collects hardware and operating system metrics such as CPU usage, memory usage, disk I/O, and network statistics from Linux-based servers.                |
| **MySQL Exporter**         | Gathers performance metrics from MySQL databases, including query durations, connection counts, and database sizes.                                       |
| **MSSQL Exporter**         | Collects metrics from Microsoft SQL Server, monitoring CPU usage, active connections, and query performance.                                              |
| **PostgreSQL Exporter**    | Exports metrics from PostgreSQL databases, including transaction counts, database sizes, and replication statistics.                                      |
| **Redis Exporter**         | Monitors Redis instances, providing metrics on memory usage, command statistics, and keyspace usage.                                                      |
| **JMX Exporter**           | Exposes Java Management Extensions (JMX) metrics from Java applications and services, allowing for monitoring of JVM performance and application metrics. |
| **Blackbox Exporter**      | Monitors the availability and response time of endpoints, such as HTTP, HTTPS, DNS, and TCP, by simulating requests.                                      |
| **Kafka Exporter**         | Collects metrics from Apache Kafka clusters, including message rates, consumer lag, and broker statistics.                                                |
| **HAProxy Exporter**       | Monitors HAProxy load balancers, providing metrics on request rates, connection counts, and response times.                                               |
| **CAdvisor**               | Monitors container metrics for Docker containers, including resource usage (CPU, memory) and container-specific metrics.                                  |
| **SNMP Exporter**          | Collects metrics from SNMP-enabled devices (such as routers and switches) by polling them for performance statistics.                                     |
| **Nginx Exporter**         | Exposes metrics from Nginx web servers, including request rates, response times, and upstream server metrics.                                             |
| **IIS Exporter**           | Collects metrics from Microsoft IIS web servers, such as request rates, connection counts, and error rates.                                               |
| **MongoDB Exporter**       | Gathers performance metrics from MongoDB databases, including operation counts, memory usage, and index statistics.                                       |
| **Bamboo Exporter**        | Exposes metrics from Atlassian Bamboo, a continuous integration and deployment tool.                                                                      |
| **Prometheus Pushgateway** | Allows for the collection of metrics from batch jobs, providing a way to push metrics into Prometheus instead of scraping them.                           |
| **Spring Boot Exporter**   | Collects metrics from Spring Boot applications, including HTTP request statistics, JVM metrics, and application-specific metrics.                         |
| **Consul Exporter**        | Gathers metrics from Consul services, including health checks and service performance statistics.                                                         |
| **Zabbix Exporter**        | Exposes metrics from Zabbix monitoring systems, allowing Prometheus to scrape Zabbix metrics.                                                             |

## Additional Notes:

- **Exporter Functionality**: Each exporter serves a specific purpose and is designed to collect metrics from a particular service or application type.
- **Installation and Configuration**: Most exporters can be easily installed and configured to expose metrics at a specific endpoint for Prometheus to scrape.

This list covers some of the most commonly used exporters in the Prometheus ecosystem. Depending on your architecture and requirements, there are many other exporters available for various services and applications.
