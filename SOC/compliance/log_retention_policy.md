# 🗂️ Log Retention Policy

## 🎯 Purpose

This policy defines how long security-related logs are retained, how they are stored, and how they are protected. It ensures that logs are available for:

- Forensics & incident response
- Compliance audits (e.g., ISO 27001, SOC 2, PCI-DSS)
- Internal accountability and risk management

---

## 🔍 Scope

This policy applies to:

- System and application logs  
- Authentication and access control logs  
- Network logs (firewalls, IDS/IPS, VPN, etc.)  
- Cloud audit logs (e.g., AWS CloudTrail, Azure Activity Logs)  
- SIEM and SOC-related alerts  
- Threat intelligence and correlation data  

---

## 🧑‍⚖️ Compliance Requirements Reference

| Standard | Requirement |
|----------|-------------|
| **ISO/IEC 27001** | A.12.4 – Logging and monitoring |
| **SOC 2 (CC7.2)** | Retain audit logs for a reasonable period |
| **NIST CSF (DE.CM-7)** | Retain logs for detection and response |
| **PCI-DSS 4.0** | Logs must be kept for **at least 1 year**, with 3 months immediately available |

---

## 🗃️ Retention Schedule

| Log Type | Minimum Retention | Access Window | Storage |
|----------|-------------------|----------------|---------|
| Authentication / Access Logs | 12 months | 3 months hot / 9 months cold | Encrypted S3 / Blob / NAS |
| Endpoint & Server Logs | 6 months | 2 months hot | Wazuh → Elasticsearch / Graylog |
| Cloud Audit Logs | 12 months | 3 months hot | S3 with lifecycle policies |
| Alert Logs (SIEM, IR) | 12 months | 3 months | TheHive, Elasticsearch |
| Network Logs (Firewall, IDS) | 6–12 months | 1–3 months | Syslog, Zeek, Suricata |
| Admin Activities / Config Changes | 12 months | 3 months | Version control or audit logs |
| Third-Party SaaS Logs | Based on vendor SLA | Sync monthly | Export via API or CSV |

---

## 🔐 Storage & Protection

- Logs must be stored **encrypted at rest**
- Logs must be **transmitted securely (TLS)**
- Only authorized personnel may access archived logs
- Audit trails must be immutable (or version-controlled)

---

## ⚙️ Open-Source Implementation Tips

| Tool | How to Use |
|------|------------|
| **Wazuh** | Define log retention under `wazuh-manager` settings |
| **Graylog** | Set retention under index settings (rotation strategy) |
| **Elasticsearch** | Use ILM (Index Lifecycle Management) for hot-warm-cold storage |
| **S3 / Azure Blob** | Configure lifecycle rules to move logs to Glacier / Archive tiers |
| **Grafana Loki** | Use object storage with retention policies |

---

## 🚨 Log Disposal

- Expired logs must be securely deleted or archived
- Deletion must be:
  - **Irreversible**
  - **Auditable**
  - **Performed in compliance with any regulatory holds**

---

## 🔄 Review Cycle

- Policy reviewed **annually** or after:
  - A major incident
  - A regulatory change
  - Infrastructure overhaul

---

## ✅ Summary Checklist

- [x] Logs are encrypted at rest and in transit  
- [x] Log retention periods are mapped to frameworks  
- [x] Lifecycle policies are applied  
- [x] Access to logs is restricted  
- [x] Archived logs are auditable and retrievable  

---

> 🔄 _Last Updated: June 27, 2025_
