
# 📊 Monitoring System using Prometheus, Grafana, Node Exporter & Alertmanager

A complete monitoring and alerting system built using Docker Compose. This project monitors Linux system resources such as CPU, Memory, Disk (SSD), File System, and Network usage. It visualizes real-time metrics using Grafana dashboards and sends email alerts whenever predefined thresholds are exceeded.

---

# 🚀 Project Overview

This project demonstrates how modern monitoring systems are implemented using open-source tools.

The monitoring stack includes:

- Prometheus for collecting metrics
- Node Exporter for exposing Linux system metrics
- Grafana for visualization
- Alertmanager for handling alerts
- Gmail SMTP for email notifications
- Docker Compose for container orchestration

---

# 🏗️ Architecture

```
                Linux System
                     │
                     │
             Node Exporter
                     │
                     ▼
               Prometheus
              /          \
             /            \
            ▼              ▼
     Alertmanager      Grafana
            │              │
            ▼              ▼
      Gmail Alerts    Dashboards
```

---

# 📁 Project Structure

```
Monitoring-System/
│
├── docker-compose.yml
├── prometheus.yml
├── rules.yml
├── alertmanager.yml
├── README.md
└── .gitignore
```

---

# ⚙️ Technologies Used

- Docker
- Docker Compose
- Prometheus
- Grafana
- Alertmanager
- Node Exporter
- PromQL
- Linux (Ubuntu)
- Gmail SMTP
- Git
- GitHub

---

# 📌 Features

- Real-time system monitoring
- CPU Usage Monitoring
- Memory (RAM) Monitoring
- Disk Usage Monitoring
- SSD Usage Monitoring
- Filesystem Monitoring
- Email Alerts
- Beautiful Grafana Dashboards
- Containerized Deployment
- PromQL Queries
- Alert Rules

---

# 📈 Metrics Monitored

## CPU Usage

Shows processor utilization.

---

## Memory Usage

Monitors RAM usage in real time.

---

## Disk Usage

Monitors Linux filesystem usage.

---

## SSD Usage

Tracks SSD utilization percentage.

---

## Network Usage

Displays network traffic.

---

## File System Usage

Shows filesystem availability and usage.

---

# 📧 Email Alerts

Configured using Gmail SMTP.

When disk usage exceeds the configured threshold, Alertmanager automatically sends an email notification.

Example Alert:

```
High SSD Usage Detected

SSD Usage: 75%

Severity: Critical

Please clean unnecessary files.
```

---

# 📊 Grafana Dashboards

Custom dashboards were created for

- CPU
- RAM
- SSD
- Disk
- Network
- Filesystem

Gauge Panels

Time Series Graphs

Stat Panels

---

# 🚨 Alert Rules

Alert rules are written in PromQL.

Example:

```promql
100 - (
node_filesystem_avail_bytes{mountpoint="/",fstype!~"tmpfs|overlay"}
*100
/
node_filesystem_size_bytes{mountpoint="/",fstype!~"tmpfs|overlay"}
) > 70
```

This triggers an alert whenever disk usage exceeds 70%.

---

# 🐳 Docker Containers

The project runs four containers:

- Prometheus
- Grafana
- Alertmanager
- Node Exporter

Launch everything using:

```bash
docker compose up -d
```

Check running containers:

```bash
docker ps
```

---

# 📦 Installation

Clone repository

```bash
git clone https://github.com/kurrashivaramakrishna/Monitoring-System.git
```

Move into project

```bash
cd Monitoring-System
```

Start containers

```bash
docker compose up -d
```

Open services

Grafana

```
http://localhost:3000
```

Prometheus

```
http://localhost:9090
```

Node Exporter

```
http://localhost:9100/metrics
```

Alertmanager

```
http://localhost:9093
```

---

# 📂 Configuration Files

## docker-compose.yml

Creates all monitoring containers.

---

## prometheus.yml

Configures scraping jobs.

---

## rules.yml

Contains Prometheus alert rules.

---

## alertmanager.yml

Contains Gmail SMTP configuration and alert routing.

---

# 🔔 Alert Workflow

```
Linux Server

↓

Node Exporter

↓

Prometheus

↓

Alert Rule

↓

Alertmanager

↓

Gmail Notification

```

---

# 🛠 Git Workflow

Initialize Git

```bash
git init
```

Add files

```bash
git add .
```

Commit

```bash
git commit -m "Initial monitoring project"
```

Connect GitHub

```bash
git remote add origin https://github.com/kurrashivaramakrishna/Monitoring-System.git
```

Push

```bash
git push -u origin main
```

---

# 🧪 Testing

Verified:

✅ Prometheus scraping

✅ Grafana dashboards

✅ Email notifications

✅ Docker networking

✅ Alert rules

✅ PromQL queries

---

# 📚 Skills Demonstrated

Docker

Docker Compose

Linux

Grafana

Prometheus

Alertmanager

PromQL

Monitoring

Observability

DevOps

Git

GitHub

Containerization

Email Alerting

Infrastructure Monitoring

---

# 🔮 Future Improvements

- Kubernetes Deployment
- Helm Charts
- Loki Log Monitoring
- Grafana Tempo Tracing
- Grafana Mimir
- SSL Security
- Cloud Deployment (AWS EC2)
- CI/CD using GitHub Actions
- Terraform Infrastructure
- Slack Notifications
- Microsoft Teams Alerts

---

# 👨‍💻 Author

**Shiva Rama Krishna Kurra**

GitHub:
https://github.com/kurrashivaramakrishna

Portfolio:
https://shivakrish.onrender.com

---

# ⭐ If you found this project useful, please consider giving it a star.
