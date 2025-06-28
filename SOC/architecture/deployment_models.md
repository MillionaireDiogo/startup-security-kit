# 🏗️ SOC Deployment Models

## 🎯 Purpose

This guide outlines possible SOC deployment models for fintech startups that want to implement practical and affordable detection and monitoring capabilities using open-source or hybrid approaches — **without relying on expensive MSSPs**.

---

## 🧩 Common Deployment Models

### 1. **All-in-One Container Stack (Starter SOC)**

Best for early-stage teams needing fast deployment with minimal overhead.

**Components:**

- Docker Compose or Kubernetes setup
- Wazuh / Graylog / Elasticsearch / Filebeat
- TheHive + Cortex
- Grafana

**Pros:**
- Fast to deploy (under 1 hour)
- Low cost (runs on a single VM or cloud instance)
- Easy to test and modify

**Cons:**
- Not scalable for high-volume environments
- Shared failure domain

---

### 2. **Distributed SOC Stack**

A production-ready setup for growth-stage teams.

**Architecture:**

| Layer | Example |
|-------|---------|
| Agents | Wazuh, OSQuery, Beats on endpoints |
| Ingestion | FluentBit/Syslog → Kafka or Redis queue |
| Aggregation | Elasticsearch, OpenSearch |
| SIEM | Wazuh/Graylog/Splunk OSS |
| IR Platform | TheHive + Cortex |
| Dashboard | Grafana, Kibana |

**Pros:**
- Scales better with data growth
- Modular and fault-tolerant
- Easier to separate duties across teams

**Cons:**
- Slightly higher setup time
- Requires automation (e.g., Terraform, Ansible)

---

### 3. **Hybrid (Cloud-Native + On-Prem Agents)**

Good for teams using cloud IaaS/PaaS but want centralized monitoring for endpoints and workloads.

**Setup:**

- Cloud-native telemetry (e.g., CloudTrail, VPC Flow Logs) to S3/Blob → ingested by self-hosted SIEM
- Endpoint agents (Wazuh, OSQuery) on VMs
- IR & alerting handled via TheHive and ticketing tools

**Pros:**
- Centralized control for multi-cloud or hybrid infrastructure
- Balances cost and performance
- Aligns with compliance (PCI-DSS, ISO 27001)

**Cons:**
- Cloud logs may incur storage costs
- Log normalization can be tricky without
