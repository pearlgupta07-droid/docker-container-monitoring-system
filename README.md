\# Docker Container Monitoring System



A real-time Docker container monitoring project built using Docker, Prometheus, cAdvisor and Grafana. It collects container metrics, visualizes resource usage and sends email notifications when CPU usage triggers an alert.



\## Project Overview



This project demonstrates how to monitor Docker containers using an open-source monitoring stack.



It provides:

\- Real-time container resource monitoring.

\- CPU and memory usage visualization.

\- Six Grafana dashboard panels.

\- CPU usage alerting.

\- Gmail email notifications through Grafana.



\## Technologies Used



| Technology | Purpose |

|---|---|

| Docker | Containerization |

| Docker Compose | Multi-container management |

| Python | Application |

| Prometheus | Metrics collection |

| cAdvisor | Container metrics |

| Grafana | Monitoring dashboards and alerts |

| Gmail SMTP | Email notifications |



\## Architecture



```mermaid

flowchart TD

&#x20;   A\[Docker Application] --> B\[cAdvisor]

&#x20;   B --> C\[Prometheus]

&#x20;   C --> D\[Grafana Dashboard]

&#x20;   D --> E\[CPU Alert]

&#x20;   E --> F\[Gmail Notification]

```



\## Services and Ports



| Service | Port | Purpose |

|---|---:|---|

| Application | 5000 | Python application |

| Prometheus | 9090 | Metrics collection |

| cAdvisor | 8080 | Container monitoring |

| Grafana | 3000 | Dashboards and alerts |



\## Project Features



1\. Container Monitoring – Monitor running Docker containers.

2\. CPU Monitoring – Track container CPU usage.

3\. Memory Monitoring – Track container memory consumption.

4\. Visualization – View metrics through six Grafana panels.

5\. Alerting – Detect high CPU usage.

6\. Email Notifications – Receive Gmail notifications when the CPU alert fires.

7\. Persistent Storage – Preserve Grafana dashboards and configuration using a Docker named volume.



\## Getting Started



\### Prerequisites



\- Docker Desktop

\- Docker Compose

\- Git



\### Installation



Clone the repository:



```bash

git clone YOUR\_GITHUB\_REPOSITORY\_URL

```



Navigate into the project:



```bash

cd docker-monitoring-system

```



Configure your environment variables in a `.env` file:



```env

GMAIL\_USER=your-email@gmail.com

GMAIL\_APP\_PASSWORD=your-gmail-app-password

```



Never upload your `.env` file or Gmail App Password to GitHub.



Start the project:



```bash

docker compose up -d --build

```



Check running containers:



```bash

docker ps

```



\### Access the Services



\- Application: http://localhost:5000

\- Prometheus: http://localhost:9090

\- cAdvisor: http://localhost:8080

\- Grafana: http://localhost:3000



\## Testing CPU Monitoring



Generate temporary CPU load:



```bash

docker run --rm ubuntu sh -c "apt-get update -qq \&\& apt-get install -y stress-ng -qq \&\& stress-ng --cpu 2 --timeout 60s"

```



Observe the CPU metrics in Grafana and verify that the configured alert sends an email notification.



\## Stopping the Project



```bash

docker compose stop

```



To start it again:



```bash

docker compose start

```



\*\*Important:\*\* Avoid `docker compose down -v` if you want to preserve your Grafana dashboard data.



\## Learning Outcomes



Through this project, I gained practical experience with:



\- Docker containerization and orchestration.

\- Prometheus metrics collection.

\- Grafana dashboard creation.

\- Container resource monitoring.

\- Alert configuration and email integration.

\- Docker volumes and persistent storage.



\## Author



\*\*Pearl Gupta\*\*



Cloud Computing Student | Aspiring Cloud Engineer





