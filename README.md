# Monitor in a Box!

This repository provides an automated kickstart environment to deploy a complete monitoring stack using **Zabbix 7.0 LTS**, **PostgreSQL 16**, and **Grafana**.

*This project was inspired by and based on the original "containers" repository by Professor Evandro José Zipf (NOTO TI) [https://github.com/josezipf/containers]. The base structure was adapted to replace MySQL with PostgreSQL and update the Grafana image to the latest release.*

## 🛠️ Tech Stack

*   **OS:** Ubuntu 24.04 LTS (Target Environment)
*   **Containerization:** Docker & Docker Compose (That's why it's called **Monitor in a Box!**)
*   **Database:** PostgreSQL 16
*   **Monitoring:** Zabbix Server, Zabbix Web, and Zabbix Agent 2 (v7.0 LTS)
*   **Visualization:** Grafana (Latest) with Alexander Zobnin's Zabbix plugin pre-provisioned

## 🎯 Features

*   **One-Click Setup:** Includes a `setup.sh` script that automatically installs Docker, configures the official repositories, and deploys the entire stack.
*   **Host Networking:** Containers run on `network_mode: host` to easily collect metrics from the local machine and the surrounding network without NAT interference.
*   **Pre-Provisioned Grafana:** Grafana automatically installs and enables the Zabbix plugin, and pre-configures the Zabbix API data source out-of-the-box.

## 🚀 How to Use

### Prerequisites

You need a fresh installation of **Ubuntu 24.04 LTS** with `sudo` privileges.

### Access

| Service | Default Port | Default Credentials |
|---------|--------------|---------------------|
| Zabbix  | 8080         | U: Admin            |
|---------|--------------| P: zabbix           |
| Grafana | 3000         | U: admin            |
|---------|--------------| P: admin            |

### Installation

```bash
git clone https://github.com/gustavawn/monitor-lab-box && cd monitor-lab-box && ./setup.sh
